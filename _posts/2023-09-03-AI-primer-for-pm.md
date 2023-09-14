---
title: "The Future-Ready PM: Navigating AI and ML in Product Management - Part 1"
excerpt: "Unveiling the real potential and limitations of AI and ML for Product Managers. Learn the key insights every PM should know to leverage Artificial Intelligence and Machine Learning for gaining a competitive edge in product development."
tags:
  - AI
  - Product Management
header:
  overlay_image: /assets/images/steve-johnson-ZPOoDQc8yMw-unsplash.jpg
  overlay_filter: 0.7 # same as adding an opacity of 0.7 to a black background
  caption: "Photo by [Steve Johnson](https://unsplash.com/@steve_j?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText) on [**Unsplash**](https://unsplash.com/photos/ZPOoDQc8yMw?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText)"
  teaser: /assets/images/steve-johnson-ZPOoDQc8yMw-unsplash.jpg
show_date: true
author_profile: true
#classes: wide
#layout: splash
published: true
# toc: true
# toc_sticky: true
#toc_label: "Table of Contexts"
#toc_icon: "python"  
#future: false
search: true
comments: true
permalink: /AI-primer-for-pm/
---

_This is Part I of the AI for PMs series. 
See [Part II](/AI-primer-for-pm-part2/) on what to pay attention to when you start building an AI product._
{: .notice--info}

# Introduction

Since OpenAI released ChatGPT last November, LLMs, GPTs, and GenAI have become buzzwords, and everyone is talking about it. Every enterprise suddenly started investing money and talent into exploring LLMs and Gen AI models. In many cases, people are mixing AI with Gen AI and simplifying LLMs and their capabilities by just calling all of them AI (thank God they are not calling them AGIs). 

In this article, I would like to demystify some misconceptions about Artificial intelligence, Machine Learning and their applications and my thoughts on what every PM needs to know regarding Artificial intelligence and Machine Learning. Spoiler Alert - AI is not a silver bullet that can magically solve all your product and customer problems and make your product a success story. Nevertheless, AI/ML has huge potential, and in the future, every product will have some AI algorithm, and eventually, every PM will become an AI Product Manager. And so understanding what and how to use AI is crucial to gaining a competitive edge through AI.

# What is AI?

The term "AI" is often used in various contexts—some even refer to it as Augmented Intelligence. Let's define our terms to ensure we're on the same page. Think of these concepts as nested Russian dolls: AI is the overarching term, under which falls ML, then Deep Learning, followed by GenAI, and finally, AGI.

![Relations between AI/ML/Deep Learning/Gen AI/AGI](/assets/images/ai_definitions.jpg){: .align-center}
*Relations between AI/ML/Deep Learning/Gen AI/AGI*

> **Artificial Intelligence (AI):** Computer systems capable of performing tasks that typically require human intelligence.
> **Machine Learning (ML):** A subset of AI focused on developing algorithms that enable computers to make decisions or predictions.
> **Deep Learning:** A specialized area within ML that utilizes multi-layer artificial neural networks to learn from large data sets.
> **Generative AI (GenAI):** Deep learning models capable of generating new data or content like images, music, video, or text.
> **Artificial General Intelligence (AGI):** The ultimate goal in the AI spectrum—a fully autonomous system capable of human-level intelligence across various tasks, without requiring specialized programming.

# Exploring the History and Diverse Fields of AI

Now that we've established a common understanding of key terms let's dive into the history of Artificial Intelligence (AI). The idea of creating artificial beings with human-like capabilities has ancient roots, featuring prominently in myths and legends like the Golem in Biblical stories or automatons in ancient mythology.

The term "Artificial Intelligence" entered the modern lexicon in 1956[^1]. Interestingly, the terms "Artificial Intelligence" and "Machine Learning" have been in the academic and cultural conversation since the late '50s, as evidenced by Google Ngram data. 

<figure class="align-center">
  <img src="/assets/images/aiml_google_ngrams.jpg" alt="AI and ML trend on Google Ngrams"/>
  <figcaption>AI and ML trend on Google Ngrams</figcaption>
</figure>


With over 70 years of research history, AI and ML have been employed across various applications, but only in the last couple of decades, advancements in technology, including the explosion of internet usage and vast amounts of data, the availability of powerful cloud computing, and specialized GPUs and AI chipsets, have catalyzed the evolution of Machine Learning algorithms and their capabilities. Today, AI and Machine Learning are at the forefront of technological innovation, influencing diverse industries such as healthcare, finance, and autonomous vehicles.

AI and ML comprise a broad landscape with numerous algorithms, approaches, and frameworks, including:

- **Computer Vision**: This area focuses on enabling machines to interpret visual data, such as images and videos.
- **Natural Language Processing (NLP)**: NLP enables computers to understand human language. Applications abound, from analyzing documents and customer feedback to translating languages and running automated customer service chatbots.
- **Reinforcement Learning**: This field enables machines to optimize their actions over time based on the consequences of past actions.
- **Time Series Algorithms**: Specialized in analyzing data points collected over time, these algorithms are beneficial in fields like finance and healthcare.
- **Anomaly Detection**: This involves identifying outliers or anomalies in data patterns, serving functions like fraud detection and network security.
- **Generative AI Models**: These algorithms create new data similar to an existing dataset, useful for generating images, text, and voice as well as augmenting data.
- **Optimization Algorithms**: These strive to find the most effective solution among a set of options and are often employed in tasks like resource allocation and scheduling.
- **Multimodal AI**: This is a form of artificial intelligence that integrates multiple types of data inputs, such as images, text, and speech, and can produce various data outputs. It's often viewed as an initial step toward AGI (Artificial General Intelligence).

Now, let's dive into different AI/ML use cases.


<!-- ![AI and ML trend on Google Ngrams](/assets/images/aiml_google_ngrams.jpg)
*AI and ML trend on Google Ngrams* -->

# AI/ML Use Cases 

Artificial Intelligence (AI) and Machine Learning (ML) technologies are revolutionizing diverse industries. Here are some notable use cases and applications where AI/ML algorithms are making a difference:

- **Personalization** - Customize user experiences based on data analytics, applicable in healthcare for personalized treatment plans, in education for adaptive learning systems, and in marketing for targeted outreach.
- **Anomaly Detection** - Flag abnormal patterns or outliers indicative of fraudulent activities, security threats, or pressing issues requiring immediate action.
- **Recommendation Systems** - Generate individualized product, service, or content suggestions commonly employed in e-commerce, streaming services, and social media to boost user engagement.
- **Image Recognition** - Utilize technology to recognize objects or anomalies in images or videos. Essential in healthcare for diagnostic imaging, in automotive industries for autonomous driving, and in security for surveillance systems.
- **Customer Insights** - Mine valuable information from customer interactions and reviews to refine products and enhance customer satisfaction.
- **Predictive Analytics** - Leverage historical data to predict future trends, behaviours, or sales, beneficial in retail, finance, and healthcare sectors.
- **Content Generation** - Automatically produce text, images, videos, or voice recordings. It is beneficial in fields like journalism, marketing, and entertainment.
- **Customer Support** - Implement chatbots for immediate, 24/7 customer assistance, enhancing service quality while cutting operational costs.
- **Natural Language Understanding (NLU)** - Employ algorithms for sentiment analysis, language translation, and text summarization. Relevant in media monitoring, global communications, and customer support.
- **Supply Chain Optimization** - Utilize AI to refine inventory management, distribution, and logistics, thereby cutting costs and elevating efficiency.
- **Healthcare Diagnostics** - Apply AI for swift and precise medical diagnoses using either medical imaging or genetic profiling.
- **Financial Risk Assessment** - Use AI algorithms to evaluate credit risks, analyze market conditions, and guide investment choices.
- **Smart Homes** - Leverage AI to control household systems like lighting and temperature to optimize energy use and boost security.
- **Traffic Management** - Apply AI in real-time data analysis for traffic regulation, signal timing adjustments, and route optimization to mitigate congestion.

# Key Considerations Before Embarking on an AI Product Journey

Multiple critical factors have to be considered before you dive into developing an AI-powered product. Understanding these can be the difference between a successful launch and a missed opportunity. 

Here are some pivotal elements to keep in mind:

**Identifying AI Opportunities** - Make sure the AI solution addresses a genuine customer need rather than merely finding an excuse to use an advanced AI model.

- Conduct market research to identify gaps or pain points that AI can solve.
- Validate the idea with stakeholders and potential users.
- **"Fall in love with the problem and not with the solution"** - Don't implement AI for the sake of adding AI to your product.

**Finding the Right Partner** - Developing AI/ML applications requires specialized expertise. Finding the right partner is crucial whether you look inside your organization or seek an external vendor.

- Evaluate potential partners based on their previous work, expertise in the domain, and customer reviews.
- Ensure that the partner aligns with your organization's culture and goals.

**Data Is Key** - If you have to build your model, data quality would be of the utmost importance. Data is the backbone of any AI project and is crucial for training models. In many cases, continuous training might also be necessary to adapt to new data patterns.

- Ensure you have access to high-quality and relevant data.
- Consider the ethical implications and legal requirements associated with data collection and usage.

**AI-Application Fit** - Understanding the pros and cons of various AI and ML techniques is essential. Discuss with your partner to choose the most appropriate algorithm for your specific problem and use case.

- Perform a feasibility analysis to identify the most effective AI or ML techniques.
- Keep scalability, cost, and performance in mind when choosing algorithms.

**Resource Allocation** - Be clear about the human and computational resources required to bring your AI project to life.

- Create a detailed project timeline and budget.
- Consider the long-term maintenance costs of the AI system.

# Conclusion

AI offers numerous opportunities for innovation in product management. Awareness of its possibilities can significantly benefit your role as a Product Manager. Be curious, follow AI trends, learn and create products that solve customer pain points and delight customers with the help of AI/ML features and algorithms. 

Check [Part 2](https://www.artkreimer.com/AI-primer-for-pm-part2/) for tips on what to pay attention to when building AI-based products. 

# Additional Resources

This article is just a primer to provide some knowledge and kick off your curiosity to learn more. Here is a short list of articles, courses and books to keep you going:

- [AI for Everyone (Coursera)](https://www.coursera.org/learn/ai-for-everyone?index=prod_all_products_term_optimization.&utm_medium=sem&utm_source=gg&utm_campaign=B2C_NAMER_ibm-data-science_ibm_FTCOF_professional-certificates_country-US-country-CA-pmax-nonNRL-within-14d&campaignid=19995348162&adgroupid=&device=c&keyword=&matchtype=&network=x&devicemodel=&adposition=&creativeid=&hide_mobile_promo&gclid=CjwKCAjw0ZiiBhBKEiwA4PT9z0U5-OHPBbnDbxNJzDXMK3G1ff6KOsrNn0v7duy_IC1ik_knIc1EKBoCX34QAvD_BwE)
- [Becoming an AI-First Product Leader (LinkedIn Learning)](https://www.linkedin.com/learning/becoming-an-ai-first-product-leader/becoming-an-ai-first-product-leader?autoplay=true&u=2142274)
- [Artificial Intelligence for Business Leaders (LinkedIn Learning)](https://www.linkedin.com/learning/artificial-intelligence-for-business-leaders/welcome-to-the-course?autoplay=true&u=2142274)
- [AI Product Management Specialization (Coursera)](https://www.coursera.org/specializations/ai-product-management-duke)
- Generative AI Landscape ([Sequoia](https://www.sequoiacap.com/article/generative-ai-a-creative-new-world/) ; [Antler](https://www.antler.co/blog/generative-ai))
- [A collection of a real-world ML applications](https://www.evidentlyai.com/ml-system-design)
- Prompt Engineering Guide: [Promptingguide.ai](http://Promptingguide.ai)
- Keep up with the latest news in the AI space with [TLDR AI](https://tldr.tech/ai)



[^1]: The field of [AI](https://en.wikipedia.org/wiki/Artificial_intelligenc research was founded at a [workshop](https://en.wikipedia.org/wiki/Dartmouth_workshop) held on the campus of [Dartmouth College](https://en.wikipedia.org/wiki/Dartmouth_College), USA during the summer of 1956.
[^2]: [Wikipedia](https://en.wikipedia.org/wiki/Deep_learning): The term *Deep Learning* was introduced to the machine learning community by Rina Dechter in 1986
[^3]: Transformer deep learning architecture that is a core of General Pretrain Models (GPT) that in turn a core of ChatGPT, was introduced in the paper ["Attention Is All You Need"](https://arxiv.org/abs/1706.03762) by Vaswani et al. in 2017
