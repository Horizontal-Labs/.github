### Quick Access:
* [Project Description](#argument-mining---uncovering-the-structure-of-persuasion-in-diverse-media)
* [Repositories](#repositories)
* [Pipeline Setup Guide](#pipeline-setup-guide)
* [Research Questions](#research-questions)

---
# Argument Mining - Uncovering the Structure of Persuasion in Diverse Media

In today's information-rich and often polarized landscape, the ability to automatically extract, analyze, and evaluate arguments from textual data has become paramount. Argument mining, a specialized area within Natural Language Processing, tackles this challenge by focusing on the identification and structuring of argumentative elements, including claims, premises, and conclusions, within written and spoken discourse.

The purpose of this project is to research, design, and develop an open-source tool for automated argument mining across diverse media formats such as social media or political debates. We aim to make (political) discourse more understandable and accessible by revealing the logical and argumentative structures embedded in natural language, leveraging the power of AI.

With its potential to enhance critical thinking and inform decision-making across diverse domains such as legal analysis, online debate platforms, policy formulation, and the detection of misinformation, argument mining provides valuable tools for understanding the logical underpinnings of persuasive communication. The anticipated outcome of this project is a functional prototype capable of processing real-world data and presenting arguments and their relationships in a structured, visual format.

Through this project, we intend to contribute to the advancement of argument mining by developing a practical and effective pipeline capable of analyzing real-world textual data and addressing the critical challenges in this evolving field.

---
# Repositories

Our project involved the creation of eight repositories. The following two are crucial for reproducing our pipeline and therefore more in detail explained both in this README ([Project Setup Guide](#project-setup-guide)) and in their repository wikis:
* **[armin-app](https://github.com/Horizontal-Labs/armin-app/wiki)**: This repository houses the web frontend, built using Vue.
* **[argument-mining-api](https://github.com/Horizontal-Labs/argument-mining-api/wiki)**: Provides the API endpoints, models, and handles the core logic for discovering Argumentative Discourse Units.

In addition, we developed other repositories for developing and testing purposes:

* **[training-zoo](https://github.com/Horizontal-Labs/training-zoo/wiki)**: Dedicated to training our decoder and encoder models.
* **[synapse-spark](https://github.com/Horizontal-Labs/synapse-spark/wiki)**: Here, we tested and engineered prompts for Large Language Models.
* **[benchmark](https://github.com/Horizontal-Labs/benchmark/wiki)**: Contains the benchmark data used to compare the results of our models.
* **[prototype-pipeline](https://github.com/Horizontal-Labs/prototype-pipeline/wiki)**: Holds our initial pipeline implementation, which was replaced by a more effective solution.
* **[argument-mining-db](https://github.com/Horizontal-Labs/argument-mining-db/wiki)**: This repository hosts our MariaDB database which was used for storing our training data.
* **[prototype-graph-visualization](https://github.com/Horizontal-Labs/prototype-graph-visualization/wiki)**: Contains testing of graph visualization.
---
# Pipeline Setup Guide

To reproduce our Argument Mining pipeline, we created this step-by-step manual to guide you thorugh it. 

## Step 1: Set up the API
To begin, you'll want to set up the **[argument-mining-api](https://github.com/Horizontal-Labs/argument-mining-api/wiki)** repository. This repository contains the core logic, models, and API endpoints for discovering Argumentative Discourse Units. It provides the foundational services that your frontend will interact with.

## Step 2: Develop the Frontend
Once the API is ready, you can begin developing your frontend using the **[armin-app](https://github.com/Horizontal-Labs/armin-app/wiki)** repository. This repository houses the Vue-based web application. It is designed to consume the endpoints provided by the argument-mining-api, allowing you to build a user interface around the API's functionality.

# Research Questions
This project investigates how modern NLP techniques, particularly transformer-based language models, can be built on to construct robust argument mining pipelines. Our research addresses the challenge of developing an effective argument mining system using an argumentation model with explicit relationship types. 

Key research questions were: 
1. **How can transformer-based language models be fine-tuned to recognize complex argumentative structures across diverse discourse types?**
      We employed LoRA (Low-Rank Adaptation) as our gine-tuning methodology, which enables adaptation of large pre-trained transformer models with minimal computational resources by training only a small subset of parameters (rank r=8 with scaling parameter α=32) rather than the entire model. Our research implemented two complementary transformer architectures, each optimized for different aspects of argument mining:
Encoder Models (ModernBERT-based): We utilized ModernBERT with a sequence classification approach featuring task-specific heads. The LoRA configuration targets critical attention and MLP components (Wqkv for query-key-value projections, Wo for attention output, and Wi for MLP inner projections). This architecture employs multi-task learning with ModernBERT serving as a shared backbone, enabling the model to learn general argumentative patterns while maintaining specialized heads for distinct argument mining tasks. The configuration is optimized for classification tasks with higher batch sizes (16) and standard BERT learning rates (2e-5). Decoder Models (TinyLlama-based): We implemented an instruction-based unified training approach using causal language modeling with targeted fine-tuning on query and value projections (q_proj, v_proj). This selective targeting reduces memory usage while focusing adaptation on the most impactful components for argumentative reasoning. The approach incorporates 4-bit quantization (QLoRA) for memory efficiency, enabling deployment of larger models with limited computational resources.

2. **How can datasets be adapted to fit a unified argumentation model that includes explicit relationship types?** 
      To unify two datasets, we developed a unified database schema centered around three core components: Argumentative Discourse Units (ADUs) as our foundational data structure that stores individual argumentative texts with their classification type and associated domain context. A domain table that captures the contextual framework for each ADU. A relationship table which explicitly models argumentative relationships between ADU pairs, categorizing connections as pro or con. This explicit relationship modeling is crucial for capturing the complex interdependencies that exist across different discourse types. The adaptation involves the following steps: structural normalisation, stance alignment and context preservation. The dataset that resulted from this was used for the training of the transformer models mentioned in (1).
3. **What trade-offs exist between model complexity, interpretability, and performance when designing argument mining systems for practical applications?** 

Further, questions centered around how a productive Argument Mining Pipeline can be deployed and hosted: 

4. **How does a suitable software architecture for an AI argument mining pipeline needs to be designed and implemented?**
   
6. **How can the results of the argument mining pipeline can be demonstrated and visualised?**

---

