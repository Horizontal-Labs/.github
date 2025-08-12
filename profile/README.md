# Argument Mining: Uncovering the Structure of Persuasion in Diverse Media

In today's information-rich and often polarized landscape, the ability to automatically extract, analyze, and evaluate arguments from textual data has become paramount. Argument mining, a specialized area within Natural Language Processing, tackles this challenge by focusing on the identification and structuring of argumentative elements, including claims, premises, and conclusions, within written and spoken discourse.

The purpose of this project is to research, design, and develop an open-source tool for automated argument mining across diverse media formats such as social media or political debates. We aim to make (political) discourse more understandable and accessible by revealing the logical and argumentative structures embedded in natural language, leveraging the power of AI.

With its potential to enhance critical thinking and inform decision-making across diverse domains such as legal analysis, online debate platforms, policy formulation, and the detection of misinformation, argument mining provides valuable tools for understanding the logical underpinnings of persuasive communication. The anticipated outcome of this project is a functional prototype capable of processing real-world data and presenting arguments and their relationships in a structured, visual format.

Through this project, we intend to contribute to the advancement of argument mining by developing a practical and effective pipeline capable of analyzing real-world textual data and addressing the critical challenges in this evolving field.

# Research Questions
This project investigates how modern NLP techniques, particularly transformer-based language models, can be built on to construct robust argument mining pipelines. Our research addresses the challenge of developing an effective argument mining system using an argumentation model with explicit relationship types. 

Key research questions include: 
- How can transformer-based language models be fine-tuned to recognize complex argumentative structures across diverse discourse types?
- How can datasets from different domains be adapted to fit a unified argumentation model that includes explicit relationship types? 
- What trade-offs exist between model complexity, interpretability, and performance when designing argument mining systems for practical applications? 

The following task is centered around how a productive Argument Mining Pipeline can be deployed and hosted. 
- How does a suitable software architecture for a AI argument mining pipeline needs to be designed and implemented?
- How can the results of the argument mining pipeline can be demonstrated and visualised?
---

## Repositories

Our project involved the creation of eight repositories. The following two are crucial for reproducing our pipeline:
* **[armin-app](https://github.com/Horizontal-Labs/armin-app/wiki)**: This repository houses the web frontend, built using Vue.
* **[argument-mining-api](https://github.com/Horizontal-Labs/argument-mining-api/wiki)**: Provides the API endpoints, models, and handles the core logic for discovering Argumentative Discourse Units.

In addition, we developed other repositories for developing and testing purposes:

* **[training-zoo](https://github.com/Horizontal-Labs/training-zoo/wiki)**: Dedicated to training our decoder and encoder models.
* **[synapse-spark](https://github.com/Horizontal-Labs/synapse-spark/wiki)**: Here, we tested and engineered prompts for Large Language Models.
* **[benchmark](https://github.com/Horizontal-Labs/benchmark/wiki)**: Contains the benchmark data used to compare the results of our models.
* **[prototype-pipeline](https://github.com/Horizontal-Labs/prototype-pipeline/wiki)**: Holds our initial pipeline implementation, which was replaced by a more effective solution.
* **[argument-mining-db](https://github.com/Horizontal-Labs/argument-mining-db/wiki)**: This repository hosts our MariaDB database. This database was used for storing our training data.
* **[graph-visualization](https://github.com/Horizontal-Labs/graph-visualization/wiki)**: Contains testing of graph visualization.



