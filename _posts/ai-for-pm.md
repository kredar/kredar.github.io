---
title: "Building AI Product: A Guide for PMs"
excerpt: "What does it take to build AI based products, Why AI products Fails and How to build AI based products"
categories:
  - AI
tags:
  - NLP
  - LLM
header:
  overlay_image: /assets/images/openai_img.jpg
  overlay_filter: 0.7 # same as adding an opacity of 0.7 to a black background
  # caption: "Photo by: [**Mariia Shalabaieva**](https://unsplash.com/it/@maria_shalabaieva?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText) on [**Unsplash**](https://unsplash.com/photos/nYSdjVD2ayo?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText)"
  teaser: /assets/images/openai_img.jpg
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

Since OpenAI released ChatGPT last November, LLMs, GPTs, Gen AI have become buzzwords and everyone is talking about it.  In many cases people are mixing AI with Gen AI and simplifying LLMs and their capabilities by just calling all them AI (thanks God they are not calling them AGIs). Every enterperises suddenly started to invest money and talent into exploring LLMs and Gen AI models. In this article I would like to demystify some concepts about Artificial intelligence, Machine Learning and their applications. I'm not an AI expert by all means but I know enough to be confident enough to talk about these topic - I did a Deeplearning.AI specialization, build some ML models from scrats, lead team of ML engineering and Data Scientists and constantly tinkering with data. 

I read Reforge article "Winning the AI Products Arms Race" several weeks ago and it didn't sit well with me. I even posted some of my thoughts and what i don't like about about Reforge's article on [Linkedin](https://www.linkedin.com/posts/artkreimer_how-to-build-ai-products-people-want-reforge-activity-7071833109175926785-Ziez?utm_source=share&utm_medium=member_desktop), but there are more to cover. Instead of talking criticizing I decided to write on this subject myself.  

This post is my take on the subject and my thoughts 

# Definitions and History

Let's start with definitions to make sure we are talking about the same thing. I heard people refer to AI as Augmented Intelligence and some other some other things. In this post I would like to use these definitions: 

>  **Artificial Intelligence or AI:** is a computer systems that can perform tasks that would typically require human intelligence.
>
> **Machine Learning or ML:** is a subset of AI that focuses on developing algorithms that enable computers to make decisions or predictions.
>
> **Deep Learning:** is a subset of machine learning that uses artificial neural networks with multiple layers to learn and identify patterns from large amounts of data.
>
> **Generative AI or GenAI:** a deep learning models that can generate new data or content, such as images, music, video or text.
>
> **Artificial General Intelligence or AGI:** AI system with human-level intelligence that can perform various tasks across different domains without specific programming. 

![Relations between AI/ML/Deep Learning/Gen AI/AGI](/Users/artiom/Documents/kredar.github.io/assets/images/ai_definitions.jpg){: .align-left}

 



Now that we are on the same page on definitions, let's talk about history of Artificial Intelligence. A notion of Artificial Intelligence is probably old as a humanity itself, with myth and legends on artificial beings with human intelligence, like Golem in Bible or automatons in acient mythology. But the field of AI research as we know it began in the middle of 20 century.    The history of Machine Learning and Artificial Intelligence dates back to the mid-20th century [^1] . The term "Artificial Intelligence" was first coined by John McCarthy in 1956 at the Dartmouth Conference, where the groundwork for the field was laid. Early AI research focused on problem-solving and symbolic methods, with the belief that AI could be achieved by manipulating symbols. Machine Learning, a subset of AI, emerged as a distinct field in the late 1980s and early 1990s. The focus of Machine Learning is to enable machines to learn from data and improve their performance over time without being explicitly programmed. The advent of the internet and the explosion of digital data drove the development of more sophisticated Machine Learning algorithms. Today, AI and Machine Learning are at the forefront of technological advancements, driving innovations in various fields such as healthcare, finance, and autonomous vehicles.

And if we look for the Artificial Intelligence and Machine Learning in Google Ngrams we can see that these terms were mentioned in the books begining from the late 50s. The term `Deep Learning` was introduced back in 1986[^2] and many methods and architecture were proposed in last century. Transformer deep learning architecture that is a core of GPTs that ChatGPT is using was introduced in the paper 

![AI and ML trend on Google Ngrams](/Users/artiom/Documents/kredar.github.io/assets/images/aiml_google_ngrams.jpg)

 

# AI/ML Use Cases

So AI models were used in many applications. Here are just some of the use cases where AI is being used: 

- **Personalization** - Use customer data to personalize experiences: treatment plans, learning, semantic search, marketing.
- **Anomaly Detection** - Identification of unusual patterns or deviations from the norm.
- **Recommendation Systems** - Personalized recommendations for products, services, or content in e-commerce, streaming platforms, and social media.
- Image Recognition - The process of identifying an object or a feature in an image or video.
- **Customer Insights** - Derive insights from customer feedback, reviews, behaviours…
- **Predictive analytics** - Forecast customer behaviour, churn, sales…
- **Content Generation** - Generate text, images, videos, voice, code…
- Customer Support - Chatbots capable of answering customer inquiring and providing customer support 24/7.





As a product managers we should be aware of 





So what to pay attention when







[^1]: The field of [AI](https://en.wikipedia.org/wiki/Artificial_intelligenc research was founded at a [workshop](https://en.wikipedia.org/wiki/Dartmouth_workshop) held on the campus of [Dartmouth College](https://en.wikipedia.org/wiki/Dartmouth_College), USA during the summer of 1956.The Turing Test was proposed by Alan Turing in 1950 and  