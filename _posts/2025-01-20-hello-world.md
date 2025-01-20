---
title: RAG vs CAG
date: 2025-01-19 23:30 +0500
categories: [LLMs, Tutorial]
tags: [RAG, CAG, AI, Machine Learning, LLMs]
author: Ishaan Ansari
---

## A Deep Dive into Retrieval-Augmented and Cache-Augmented Generation


The AI space is abuzz with discussions around Cache-Augmented Generation (CAG). Let’s break down the differences between Retrieval-Augmented Generation (RAG) and this newer approach, and explore their unique strengths and challenges.

### RAG in Action
The steps for implementing naive RAG: \\
1️⃣ Embed the user query for contextual search via vector databases—or skip this step if no contextual search is needed. \\
2️⃣ Retrieve relevant context from the database or another source. \\
3️⃣ Combine the user query with a system prompt for answer generation.\\
4️⃣ Enrich the prompt with the retrieved context. \\
5️⃣ Generate and deliver the final answer to the user.

### CAG Simplified
Here’s how CAG operates: \\
1️⃣ Pre-compute external context into a key-value (KV) cache for the LLM, storing it in memory. This step is one-and-done! \\
2️⃣ Use a system prompt that guides the LLM on leveraging the cached context to generate a response. \\
3️⃣ Return the generated answer. Afterward, clear temporary generations but keep the original cached context for subsequent queries.

### Thoughts on CAG
➡️ Not entirely new: While described in a recent white paper, variations of CAG have been around since OpenAI and Anthropic introduced prompt caching. \\
❌ Accuracy concerns: LLMs still struggle with accuracy when handling very long contexts. \\ 
❌ Security challenges: CAG’s inability to isolate data makes it risky for enterprise use. \\ 
❌ Dynamic data limitations: Constantly changing data requires frequent recomputation of the KV cache. \\
✅ Strengths in static scenarios: CAG shines when working with static, non-sensitive data. \\ 
✅ Power of hybrid models: Combining RAG and CAG unlocks exciting possibilities—stay tuned for more insights on  this!

💡Have you experimented with CAG yet? What are your thoughts? 


Hope you found this article useful. If you have any questions, you can check my [blog's repo](https://github.com/ishaan-ansari/iansari.github.io) on Github or feel free to reach out to me on [Twitter](https://twitter.com/iamihansari) or [LinkedIn](https://www.linkedin.com/in/ishaanansari/).


