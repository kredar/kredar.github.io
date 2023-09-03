---
title: "Building a Resume Chatbot powered by OpenAI GPT3.5 model"
excerpt: "Crafting a Smarter Resume Bot: A Guide to Leveraging Langchain, Vector DB, and OpenAI"
categories:
  - Gen-AI
  - LLM
tags:
  - NLP
  - LLM
  - AI
header:
  overlay_image: /assets/images/neural_net_midjourney.png
  overlay_filter: 0.7 # same as adding an opacity of 0.7 to a black background
  # caption: "Image by: [**Midjourney**](https://www.midjourney.com/app/)"
  teaser: /assets/images/neural_net_midjourney.png
show_date: true
author_profile: true
classes: wide
#layout: splash
published: true
toc: true
toc_sticky: true
#toc_label: "Table of Contexts"
#toc_icon: "python"  
---


# Introduction

In my previous post [Exploring the Power of LLMs for NLP Tasks"](https://www.artkreimer.com/gen-ai/ai/How-to-Analyze-App-Reviews-Using-GPT/) I explored how Language Learning Models (LLMs) can be utilized for a range of Natural Language Processing (NLP) tasks —sentiment analysis, topic extraction, content generation, summarization, and more. Building on that foundation, this post aims to guide you through my journey of crafting a personal/resume chatbot. This chatbot is powered by OpenAI's GPT-3.5, Langchain, and Streamlit. You can test drive my resume bot  [here](https://www.artkreimer.com/gen-ai/llm/Resume-Bot-powered-by-llm/#demo) 

# The Motivation Behind the Chatbot

I wanted a chatbot that could serve as a personal assistant—one designed to answer questions about my professional experience, educational background, and career aspirations, essentially a resume bot. Last year, I began this project using Google Dialogflow CX. Anyone in the Conversational AI space will concur that crafting an excellent chatbot experience on such platforms can be challenging and time-consuming. Although I had a working prototype, it still required extensive testing and tweaks in both conversational design and intent training. However, the game changed with the release of OpenAI's GPT-3.5 Turbo model. I pivoted to using large language models (LLMs), resulting in a resume chatbot built with Langchain, FAISS for vector database management, all showcased through a Streamlit frontend.

# Overview of the Logic Architecture

I use a standard architecture commonly used in Retrieval Augmented Generation (RAG) applications. Retrieval-augmented generation (RAG) is an AI framework that combines an information retrieval component with an LLM foundational model for text generator model. It works by retrieving data that is not present in a foundation model and added to the prompts to retrive the relevant data. It allows foundational model to generate text that it had no knowledge about. It also allows to update the data without retraining or finetuning the model, enabling access to the latest information for generating reliable outputs via retrieval-based generation. This approach also helps to reduce hallucinations in GenAI applications and improve the quality of LLM-generated responses.  

This architecture is designed to:

1. Create embeddings for all documents.
2. Store these embeddings in a vector database for rapid retrieval.

## Data Storage

My data is stored in simple CSV file, featuring just two columns `question` and `answer`. I created this data for my Dialogflow CX prototype so i just converted it to a CSV format for this project. Each row in this file serves as a source for generating an individual embedding vector. Here is how the data looks like. 

```csv
question,answer
who is art kreimer, Art Kreimer is a seasoned Product leader ....
```

## The Process Flow

Upon receiving a user's message, the system:

1. Generates an embedding for the query.
2. Identifies the most closely aligned vectors from the stored documents.
3. Sends the user query, along with the retrieved documents and a specific prompt, to the LLM.
4. Present the answer to user

For more information about LLM based application architecture check out these two articles: 

* [Patterns for Building LLM-based Systems & Products](https://eugeneyan.com/writing/llm-patterns/#retrieval-augmented-generation-to-add-knowledge)
* [Emerging Architectures for LLM Applications](https://a16z.com/2023/06/20/emerging-architectures-for-llm-applications/) 

# Code Deep Dive 

## Libraries

I'm using three main tools for this chatbot:

- Langchain to manage the RAG flow
- FAISS to store embeddings and retrieve documents. Alternative vectore DBs are: Chroma, Pinecone, and many others. 
- Streamlit for UI
- OpenAI gpt-3.5-turbo for information retrival

Here's what the Python code looks like to bring these tools together:

```python  
import os
import streamlit as st
from langchain.embeddings.openai import OpenAIEmbeddings
from langchain.chat_models import ChatOpenAI
from langchain.chains import ConversationalRetrievalChain
from langchain.document_loaders.csv_loader import CSVLoader
from langchain.vectorstores import FAISS
from langchain.prompts import load_prompt
```



## Making the Bot Talk Right: The Prompt

Getting the chat Streamlit interface to look nice was one thing, but I spent even more time figuring out how the chatbot should talk. I tested a lot of different prompts before settling on one that works well for this task. It's mostly accurate, but probably can be improved even more. 

Here's the Python code for the prompt:

```python
""" System: You are a CareerBot, a comprehensive, interactive resource for exploring Artiom (Art) Kreimer's background, skills, and expertise. 
Be polite and provide answers based on the provided context only. Use only the provided data and not prior knowledge.
Human: Follow exactly these 3 steps:
1. Read the context below 
2. Answer the question using only the provided Help Centre information
3. Make sure to nicely format the output so it is easy to read on a small screen.
Context : {context} 
User Question: {question}
If you don't know the answer, just say you don't know. 
Do NOT try to make up an answer.
If the question is not related to the information about Artiom Kreimer, 
politely respond that you are tuned to only answer questions about Artiom Kreimer's experience, education, training and his aspirations. 
Use as much detail as possible when responding but keep your answer to up to 200 words.
At the end ask if the user would like to have more information or what else they would like to know about Art Kreimer."""
```



## Logic

1. **API Keys**: Fetches OpenAI API keys from either the environment variables when it runs locally or Streamlit's secrets when it runs from Streamlit cloud.

```python
if "OPENAI_API_KEY" in os.environ:
    openai_api_key = os.getenv("OPENAI_API_KEY")

else: openai_api_key = st.secrets["OPENAI_API_KEY"]
```


2. **Data and Embeddings**: Loads the dataset from a CSV file and creates FAISS vectors for quick searching.

```python
path = os.path.dirname(__file__)
#my_file = path+'/photo.png'

# Loading prompt to query openai
prompt = load_prompt(path+"/templates/template1.json")
#prompt = template.format(input_parameter=user_input)

# loading embedings
faiss_index = path+"/faiss_index"

# Loading CSV file
data_source = path+"/data/about_art_chatbot_data.csv"

# Creating embeddings for the docs
if data_source :
    loader = CSVLoader(file_path=data_source, encoding="utf-8")
    data = loader.load()
    embeddings = OpenAIEmbeddings()
    
    #using FAISS as a vector DB
    if os.path.exists(faiss_index):
        vectors = FAISS.load_local(faiss_index, embeddings)
    else:
        vectors = FAISS.from_documents(data, embeddings)
        vectors.save_local("faiss_index")
    retriever=vectors.as_retriever()
```

3. **Langchain Chain**: Sets up a Conversational Retrieval Chain using Langchain, which combines GPT-3.5 and the FAISS vectors for responding to queries.

```python
#Creating langchain retreval chain 
chain = ConversationalRetrievalChain.from_llm(llm = ChatOpenAI(temperature=0.0,model_name='gpt-3.5-turbo', openai_api_key=openai_api_key), 
                                                retriever=retriever,return_source_documents=True,verbose=True,chain_type="stuff",
                                                max_tokens_limit=4097, combine_docs_chain_kwargs={"prompt": prompt})
```

4. **Chat Logic**: Defines the logic for handling the conversation and maintaining chat history in Streamlit's session state.

```python
def conversational_chat(query):
    result = chain({"system": 
    "You are a CareerBot, a comprehensive, interactive resource for exploring Artiom (Art) Kreimer's background, skills, and expertise. \
    Be polite and provide answers based on the provided context only. Use only the provided data and not prior knowledge.", 
                    "question": query, 
                    "chat_history": st.session_state['history']})
    st.session_state['history'].append((query, result["answer"]))
    
    if 'I am tuned to only answer questions' in result['answer']:
        return(result["answer"])
    else: return(result["answer"])
```


5. **Streamlit UI for chat**: Initializes the UI, displays prior messages, and manages the user input and bot responses.

```python
#Creating Streamlit title and adding additional information about the bot
st.title("Art Kreimer's resume bot")
with st.expander("⚠️Disclaimer"):
    st.write("""This is a work in progress chatbot based on a large language model.\
     It can answer questions about Art Kreimer""")
    
    if "openai_model" not in st.session_state:
    st.session_state["openai_model"] = "gpt-3.5-turbo"

if "messages" not in st.session_state:
    st.session_state.messages = []

if 'history' not in st.session_state:
    st.session_state['history'] = []

for message in st.session_state.messages:
    with st.chat_message(message["role"]):
        st.markdown(message["content"])

if prompt := st.chat_input("Hi, I'm CareerBot. Ask me about Art's skills, background, or education!"):
    st.session_state.messages.append({"role": "user", "content": prompt})
    with st.chat_message("user"):
        
        user_input=prompt
        st.markdown(prompt)

    with st.chat_message("assistant"):
        message_placeholder = st.empty()
        full_response = ""
        full_response = conversational_chat(user_input)
        message_placeholder.markdown(full_response)
    st.session_state.messages.append({"role": "assistant", "content": full_response})
```

# Conclusion

Developing this resume bot, which leverages Streamlit, Langchain, FAISS, and the OpenAI GPT-3.5 foundational model using the RAG architecture, has been an invaluable learning experience. The RAG architecture shows significant promise; I foresee a growing number of companies incorporating this approach into their language model-based applications.

## Lessons Learned

1. **Prompt Tuning**: Perfecting the prompt requires extensive trial and error to obtain accurate and context-relevant answers from the language model.
2. **Data Quality**: The intelligence of your chatbot is directly proportional to the quality of data you feed it.
3. **Chat History**: Utilizing chat history is crucial for refining the chatbot's responses.
4. **Hallucinations**: Although RAG and prompt engineering have substantially reduced hallucinations, they haven't eliminated them entirely. An additional validation step in the architecture could further mitigate this issue.
5. **Data Management and Retrieval**: Vector-based searches have proven effective for long and complex queries. However, this approach could benefit from adding keyword-based search methods like TF-IDF or BM25 for short queries or keyword searches. Additionally, it's important to partition your data into manageable segments to avoid exceeding the 4K token limit imposed by the GPT-3.5 model and improving quality of your answers.
6. **Number of Chat Turns**: Another consideration is to limit the number of chat turns to manage the prompt size more effectively.
7. **Responsiveness**: The chain I've developed operates at a slower pace than desired. While functional, it requires further optimization for speed.
8. **Not Production-Ready**: This project served as an excellent learning experience, but it's not yet ready for production deployment. Additional steps such as testing, prompt refinement, logging, monitoring, caching for better responsiveness, as well as input and response validation are essential to make it production-grade.

# Demo

You can try my resume bot below or on [Streamlit Cloud](https://art-career-bot.streamlit.app/)

<iframe
  src="https://art-career-bot.streamlit.app/?embed=true"
  height="900"
  style="width:100%;border:none;"
></iframe>





