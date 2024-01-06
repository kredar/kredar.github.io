---
title: "Beyond the Buzz: AI primer for Product Managers"
excerpt: "Learn the key AI/ML concepts every PM should know."
categories:
  - Product Management
tags:
  - AI
  - Product Management
header:
  overlay_image: /assets/images/header/ai_primer_h.jpg
  overlay_filter: 0.5 # same as adding an opacity of 0.7 to a black background
  # caption: "Photo by [Steve Johnson](https://unsplash.com/@steve_j?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText) on [**Unsplash**](https://unsplash.com/photos/ZPOoDQc8yMw?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText)"
  teaser: /assets/images/feature_row/ai_primer_f.jpg
  og_image: /assets/images/header/ai_primer_h.jpg
show_date: true
#author_profile: true
#classes: wide
#layout: splash
published: true
toc: true
toc_sticky: true
#toc_label: "Table of Contexts"
#toc_icon: "python"  
#future: false
search: true
comments: true
permalink: /AI-primer-for-pm/
---

_This is Part I of the AI for PMs series. See [AI for PMs - Part II](/AI-primer-for-pm-part2/) on what to pay attention to when you start building an AI product._
{: .notice--info}

## Introduction

Today, AI / ML is at the cutting edge of technological innovation, impacting various sectors from healthcare to finance. Since OpenAI launched ChatGPT late last year, terms like LLMs, GPT, and GenAI have become buzzwords. Product hunt is filled with GenAI-based products, and the AI product landscape is growing exponentially [^0]. This article aims to clarify some misconceptions about AI and ML and what Product Managers need to know about them. While AI isn't a cure-all, understanding its capabilities is key to competitive advantage.	

It's worth noting that the concept of AI is not new; it has ancient origins and has been part of human imagination for centuries, appearing in myths like the Biblical Golem and ancient automatons. The term 'Artificial Intelligence' itself was coined in 1956[^1] and has been a subject of academic and cultural discussion ever since. With over 70 years of research history, AI and ML have been employed across various applications, but only in the last couple of decades, advancements in technology, including the explosion of internet usage and vast amounts of data, the availability of powerful cloud computing, as well as specialized GPUs and AI chipsets, have catalyzed the evolution and improvements of ML models. 

<figure class="align-center">
  <img src="/assets/images/aiml_google_ngrams.jpg" alt="AI and ML trend on Google Ngrams"/>
  <figcaption>AI and ML trend on Google Ngrams</figcaption>
</figure>



## So, what is AI?

AI is an umbrella term covering various subfields, including Machine Learning (ML), Deep Learning, Generative AI (GenAI), and the ultimate goal, Artificial General Intelligence (AGI). Let's go over the definitions:

Artificial Intelligence (AI) 
: Computer systems capable of performing tasks that typically require human intelligence. 

Machine Learning (ML) 
: A subset of AI focused on developing algorithms that enable computers to make decisions or predictions. 

Deep Learning 
: Specialized area within ML that utilizes multi-layer artificial neural networks to learn from large data sets. 

Generative AI (GenAI) 
: Deep learning models capable of generating new data or content like images, music, video, or text. 

Artificial General Intelligence (AGI) 
: The ultimate goal in the AI spectrum—a fully autonomous system capable of human-level intelligence across various tasks without requiring specialized programming. 

## Types of ML

There are four main types of ML models: 

1. **Supervised Learning**: The model is trained on labelled data to make predictions or decisions.

    Applications: Credit score applications, email spam detection, news topic classifications, and image recognition. 

2. **Unsupervised Learning**: The model uses unlabeled data to find patterns or groupings.

   Applications: Document clustering, customer segmentation based on buying behaviour, anomaly detection. 

3. **Semi-supervised Learning**: The model uses both labelled and unlabeled data for training, often to improve performance.

   Applications: Image recognition and other supervised learning applications. 

4. **Reinforcement Learning**: The model learns to make decisions by interacting with an environment to achieve a goal or maximize some notion of cumulative reward.

   Applications: Game playing, Autonomous vehicles.

Now, let's dive into different AI/ML use cases.

## AI/ML Use Cases 

Artificial Intelligence (AI) and Machine Learning (ML) technologies are revolutionizing diverse industries. Here are some notable use cases and applications where AI/ML algorithms are making a difference:

- **Credit Scoring & Anomaly Detection**: Often use Supervised and Unsupervised Learning models.
- **Chatbots & Customer Service & Customer Insights**: Primarily rely on NLP, which can be built using Supervised Learning.
- **Stock Trend Analysis**: Typically use Time Series Algorithms, a form of Supervised Learning.
- **Content Generation**: Generative AI models to generate text, audio, code and video using form of Deep Learning that uses both Supervised and Unsupervised ML models, 
- **Supply Chain Optimization**: Utilizes Optimization Algorithms, often built using Reinforcement Learning.
- **Recommendation Systems**: Generate individualized product, service, or content suggestions commonly employed in e-commerce, streaming services, and social media to boost user engagement. Both supervised and unsupervised models are being used. 

## Key Considerations Before Embarking on an AI Product Journey
Multiple critical factors have to be considered before you dive into developing an AI-powered product. Understanding these can be the difference between a successful launch and a missed opportunity. 

Here are some pivotal elements to keep in mind:

**Identifying AI Opportunities** - Make sure the AI solution addresses a genuine customer need rather than merely finding an excuse to use an advanced AI model.
- Conduct market research to identify gaps or pain points that AI can solve.
- Validate the idea with stakeholders and potential users.
- **"Fall in love with the problem and not with the solution"** - Don't implement AI for the sake of adding AI to your product.

**Finding the Right Partner** - Developing AI/ML applications requires specialized expertise. Finding the right partner is crucial whether you look inside your organization or seek an external vendor.
- Evaluate potential partners based on their previous work and their expertise in the domain.
- Ensure that the partner aligns with your organization's culture and goals.

**Data Is Key** - If you have to build your model, the right data and its quality would be of the utmost importance. Data is the backbone of any AI project and is crucial for training models. In many cases, continuous training might also be necessary to adapt to new data patterns.

- Ensure you have access to the right amount of a high-quality and relevant data.
- Consider the ethical implications and legal requirements associated with data collection and usage, more about it in my next [post](/AI-primer-for-pm-part2). 

**AI-Application Fit** - Understanding the pros and cons of various AI and ML techniques is essential. Discuss with your partner to choose the most appropriate algorithm for your specific problem and use case.

- Perform a feasibility analysis to identify the most effective AI or ML techniques.
- Keep scalability, cost, and performance in mind when choosing algorithms.

**Resource Allocation** - Be clear about the human and computational resources required to bring your AI project to life.
- Create a detailed project timeline and budget.
- Consider the long-term maintenance costs of the AI system.

## Conclusion
AI offers numerous opportunities for innovation in product management. Awareness of its possibilities can significantly benefit your role as a Product Manager. Be curious, follow AI trends, learn and create products that solve customer pain points and delight customers with the help of AI/ML features and algorithms. 

Check [AI for PMs - Part 2](https://www.artkreimer.com/AI-primer-for-pm-part2/) for tips on what to pay attention to when building AI-based products. 

## Additional Resources

This article is just a primer to provide some knowledge and kick off your curiosity to learn more. Here is a short list of articles, courses and books to keep you going:

- [AI for Everyone (Coursera)](https://www.coursera.org/learn/ai-for-everyone?index=prod_all_products_term_optimization.&utm_medium=sem&utm_source=gg&utm_campaign=B2C_NAMER_ibm-data-science_ibm_FTCOF_professional-certificates_country-US-country-CA-pmax-nonNRL-within-14d&campaignid=19995348162&adgroupid=&device=c&keyword=&matchtype=&network=x&devicemodel=&adposition=&creativeid=&hide_mobile_promo&gclid=CjwKCAjw0ZiiBhBKEiwA4PT9z0U5-OHPBbnDbxNJzDXMK3G1ff6KOsrNn0v7duy_IC1ik_knIc1EKBoCX34QAvD_BwE)
- [Becoming an AI-First Product Leader (LinkedIn Learning)](https://www.linkedin.com/learning/becoming-an-ai-first-product-leader/becoming-an-ai-first-product-leader?autoplay=true&u=2142274)
- [Artificial Intelligence for Business Leaders (LinkedIn Learning)](https://www.linkedin.com/learning/artificial-intelligence-for-business-leaders/welcome-to-the-course?autoplay=true&u=2142274)
- [AI Product Management Specialization (Coursera)](https://www.coursera.org/specializations/ai-product-management-duke)
- Generative AI Landscape ([Sequoia](https://www.sequoiacap.com/article/generative-ai-a-creative-new-world/) ; [Antler](https://www.antler.co/blog/generative-ai))
- [A collection of a real-world ML applications](https://www.evidentlyai.com/ml-system-design)
- Prompt Engineering Guide: [Promptingguide.ai](http://Promptingguide.ai)
- Keep up with the latest news in the AI space with [TLDR AI](https://tldr.tech/ai)

<div style="text-align: center;">
<iframe src="https://artkreimer.substack.com/embed" title="Newspaper sign up" height="320" width="400" style="border:1px solid #EEE; background:white;" frameborder="0" scrolling="no" ></iframe>
</div>

[^0]: AI and GenAI landscape is enormous. Here are some examples: [Sequoia GenAI](https://www.sequoiacap.com/article/generative-ai-a-creative-new-world/), [DataCamp](https://www.datacamp.com/cheat-sheet/the-generative-ai-tools-landscape)
[^1]: The field of [AI research](https://en.wikipedia.org/wiki/Artificial_intelligence) was founded at a [workshop](https://en.wikipedia.org/wiki/Dartmouth_workshop) held on the campus of [Dartmouth College](https://en.wikipedia.org/wiki/Dartmouth_College), USA during the summer of 1956.
[^2]: From [Wikipedia](https://en.wikipedia.org/wiki/Deep_learning): The term *Deep Learning* was introduced to the machine learning community by Rina Dechter in 1986
[^3]: Transformer deep learning architecture that is a core of General Pretrain Models (GPT) that in turn a core of ChatGPT, was introduced in the paper ["Attention Is All You Need"](https://arxiv.org/abs/1706.03762) by Vaswani et al. in 2017
