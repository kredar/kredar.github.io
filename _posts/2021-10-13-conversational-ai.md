---
title: "Conversational AI and its future"
categories:
  - Conversational AI
tags:
  - Virtual Assistant
excerpt: "What is conversational AI and how it would evolve"
header:
  overlay_image: /assets/images/chatbot-image.jpeg
  overlay_filter: 0.7 # same as adding an opacity of 0.7 to a black background
  # caption: "Photo credit: [**freestocks**](https://unsplash.com/@freestocks?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText) on [Unsplash](https://unsplash.com/s/photos/phone-conversation?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyTex)"
show_date: true
author_profile: true
classes: wide
#layout: splash
published: true
---

# The Future of Conversational AI

I recently discussed the current state of Conversational AI and its future. It was a great discussion, and I thought to share some of it here. But first, let's talk about what is Conversational AI? 

**Conversational AI** is a combination of various tools, frameworks, and machine learning models that allow humans to interact with the technology using natural language. It could be a chatbot on a website or social messaging app, a smart speaker like Amazon Echo, or Conversational IVR in the telephony system. In other words, Conversational AI can communicate like a human by recognizing speech or text, understanding human's intent,  and responding in a way that mimics human conversation.

Conversational AI or chatbots is not something new. The first chatbot, [ELIZA](https://en.wikipedia.org/wiki/ELIZA), was created back in 1966. But only in the last decade, we saw massive investments, advancements, and interest in Conversational AI for enterprise applications.

## Conversational AI use cases

There are many reasons why companies want to add a conversational AI interface to their products, from providing better 24/7 customer support to replacing old [IVR](https://en.wikipedia.org/wiki/Interactive_voice_response) systems with a Conversational IVR. Any interface where customers can interact with a brand can be enhanced or even transformed with Conversational AI. Companies can add Conversational capabilities to the website, mobile app, social pages, and phone systems. Some would argue that Conversational AI is a table stake[^tablestake].

Here are some of the more obvious use cases for conversational AI:

1. Customer Support
2. E-commerce
3. Lead generation
4. General inquiries
5. Info collection
6. Product Education and On-boarding 
7. Personal Finance Management

Companies can also use it internally to improve their employees' experience:

1. On-boarding
2. IT Helpdesk
3. HR support
4. Workflow automation
5. Customer Support Agent assistance and coaching

Like with any product you are building, focus on customer experience. Make sure you define customer-centric KPIs to guide you during the platform selection, UX design and solution architecture. 

## Conversational AI architecture

Enterprise Conversational AI implementation would include multiple components, ML models and services. Here are some of them: 

- Text to Speech
- Speech to Text also known as ASR
- Natural Language Understanding 
- Natural Language Generation
- Conversation Dialog management 
- Telephony System
- Live Chat platform
- Business logic automation
- Robotic Process Automation (RPA)

And high-level architecture would look like this:
![Conversational AI Architecture](/assets/images/conv_ai_architecture.png)



### Build vs Buy

Building the whole conversational AI stack would be a huge project, and I wouldn't recommend doing it. Many components became a commodity. I would suggest buying most of the components available on the market and developing what is unique to your organization. When choosing a conversational AI platform don't forget to check:  
- Platform maturity 
- Hosting 
- Scalability 
- Integration with Livechat providers 
- Accessibility 
- Analytics
- Pricing
- And many other features 

There are many Conversational AI platforms available on the market. Every big cloud provider has one; most of the livechat providers recently added this capability; various startups and open source frameworks. Each one of these platforms has its pros and cons. I am not going to review them, I am just going to name a few:

![Conversational AI Platforms](/assets/images/conv_ai_platforms.png)


### Team

Once you decided on the platform you need talent to design, implement and maintain your Conversational experience. Without proper talent your project will fail. At the very least, you would need the following experts in various capacities throughout the project:

- Conversational UX designers
- Conversational AI developers
- NLP trainers
- Data Analysts and Data Scientists
- Software developers
- Machine Learning developers

As you can see, Conversational AI is complex and requires substantial investments to create a great customer experience. This is why not many enterprises have conversational AI implementations. Still, I am sure most of them are working on one or planning to implement it soon. 

## The Future of Conversational AI

COVID-19 accelerated digital transformation in general and pushed companies to accelerate their efforts in adding Conversational AI solutions to their websites, IVRs, social channels, etc. A lot of new startups popped up specializing in Conversational AI tools and frameworks. Investors made significant investments in Conversational AI startups in the last 18 months[^investments]. At the same time, big players like Google, Microsoft, Amazon continue to invest heavily in their Conversational AI offers and acquire or invest in startups and AI research companies[^msft_invest]. 

I envision simplification and enhancements of conversational AI tools for enterprises:

-   Simplified NLP training that requires less training data 
-   Pretrained domain-specific NLP models 
-   Conversational templates
-   Truly self-learning capabilities, like information extraction from previous conversations and model adjustments
-   Adoption of codex-like capabilities - translation of human language to a code[^codex]. It would greatly simplify bot development.
-   More professionals with conversational AI skills 

With all the capital investments and latest breakthroughs in NLP/NLU space (better ASR, Intent Classification, TTS models), new courses specializing in [conversational UX design](https://voicetechglobal.com/conversation-design-training/),  more and more professionals investing in their conversational AI skills, we are about to see more and more enterprise chatbot and voicebot implementations with great user experience. I expect that in 5 years, every enterprise will have conversational AI implementation on their website, mobile app, social channel, as well as internal virtual assistants. Having Conversational AI is already considered a table stake[^tablestake], and in 5 years, it will be everywhere. 

Conversational AI is quickly evolving, and we are about to see a lot of innovations in this space and great Conversational AI implementations. It feels great to be part of this evolution, and I look forward to experiencing it.

[^codex]: I was especially impressed by the OpenAI's [Codex demo](https://www.youtube.com/watch?v=SGUCcjHTmGY). Codex is a GPT-3 based model that can translate human language into a programming code. Imaging that you don't have to write a code to retrieve information from the database but all you have to do is to train ML model on your enterprise APIs, so when customer asks `what is my balance?` model translated this into a code and retrieve this information from the backend system.  
[^5]: Transformer models, like OpenAI's GPT-3, Google's T5, [Microsoft  MT-NLG](https://www.microsoft.com/en-us/research/blog/using-deepspeed-and-megatron-to-train-megatron-turing-nlg-530b-the-worlds-largest-and-most-powerful-generative-language-model/) showing breakthrough performance on wide range of NLP tasks like text summarization, text generation, reading comprehension, common sense reasoning, etc. 
[^msft_invest]: Microsoft invested $1B in OpenAI in 2019, and this year acquired [Nuance](https://www.forbes.com/sites/joecornell/2021/04/20/microsoft-announces-acquisition-of-nuance-targets-completion-in-2021/?sh=4e9bc4055bbe) for estimated $19B . Last December Google released a new version of their Conversational AI tool Dialogflow CX. Amazon released V2 version of Amazon Lex back in January this year. 

[^investments]: Here are some notable ones in the last 18 months: [Rasa raises $26M, June 2020](https://techcrunch.com/2020/06/23/rasa-raises-26m-led-by-a16z-for-its-open-source-conversational-ai-platform/); [Ada raised $44M in Mar, 2020 and $130M in May, 2021](https://www.ada.cx/posts/130m-raised-in-series-c-round) ; [Cognigy raises $44M, June 2021](https://techcrunch.com/2021/06/01/cognigy-raises-44m-to-scale-its-enterprise-focused-conversational-ai-platform/) ; [Yellow.AI raises $78M, Aug 2021](https://venturebeat.com/2021/08/04/yellow-ai-raises-78m-to-expand-its-ai-chatbot-platform-globally/) ; [Kore.ai raises $50M, Sept 2021](https://siliconangle.com/2021/09/29/kore-ai-raises-50m-ai-powered-experience-optimization-platform/) ; [Leena AI raises $30M, Sept 2021](https://venturebeat.com/2021/09/28/enterprise-focused-conversational-ai-platform-leena-ai-raises-30m/?utm_campaign=Daily%20Roundup&utm_medium=email&utm_source=Revue%20newsletter) ; As well as investments in Conversational AI Design tools [Voiceflow raises $20M](https://www.forbes.com/sites/igorbosilkovski/2021/07/29/canadian-conversational-ai-design-tool-voiceflow-raises-20-million-in-series-a/?sh=5aa772eb46cf)
[^tablestake]: [Every bank needs a chatbot or two](https://www.forbes.com/sites/ronshevlin/2021/03/15/every-bank-needs-a-chatbot-or-two-for-its-digital-transformation/?sh=35f096f275d7)
[^2]: The Turing test, originally called the imitation game by Alan Turing in 1950, is a test of a machine's ability to exhibit intelligent behaviour equivalent to, or indistinguishable from, that of a human. https://en.wikipedia.org/wiki/Turing_test