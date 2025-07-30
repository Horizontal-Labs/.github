# Argument Mining: Uncovering the Structure of Persuasion in Diverse Media

In today's information-rich and often polarized landscape, the ability to automatically extract, analyze, and evaluate arguments from textual data has become paramount. Argument mining, a specialized area within Natural Language Processing, tackles this challenge by focusing on the identification and structuring of argumentative elements, including claims, premises, and conclusions, within written and spoken discourse.

The purpose of this project is to research, design, and develop an open-source tool for automated argument mining across diverse media formats such as social media or political debates. We aim to make (political) discourse more understandable and accessible by revealing the logical and argumentative structures embedded in natural language, leveraging the power of Machine Learning (!needs later revision!) techniques.

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

# Approaches for Argument Mining Language Model

To address the outlined research questions, this project explores and evaluates multiple transformer-based approaches to argument mining.
These approaches represent different architectures of language models and learning techniques for capturing argumentative structures in text. Each will be evaluated for its effectiveness, practicality, and alignment with the project's goals. 

1. **Encoder**  
These models process input text through a transformer encoder (e.g. BERT, RoBERTa) to produce contextualized token embeddings, which are then used for downstream classification tasks.  
- **Multi-Task Finetuning:** A single encoder is fine-tuned using multiple classification heads, each tailored to a subtask such as argument component identification (e.g., claims, premises) and relation classification (e.g., pro, con).  
2. **Decoder**  
Decoder-only models (e.g. GPT) can be utilized through prompting to classify argument structures in a generative fashion.  
- **Prompting / In-context learning (Zero Shot / Few Shot):** This approach makes use of the in-context learning abilities of LLMs by only using prompts that guide the pre-trained model to perform argument mining without additional training.  
- **Multi Task Instruction-based Finetuning:** The model is fine-tuned using an instruction-based format, where tasks are framed as textual commands.  
3. **Encoder-Decoder**  
Encoder-Decoder Models (e.g. T5 / BART) offer an architecture for both classification and generation tasks.  
- **Prompting / In-context learning (Zero Shot / Few Shot):** Similar to decoder-only models, encoder-decoder models can be used with tailored prompts to extract argument structures, taking advantage of their ability to produce structured outputs (embeddings).

Further information can found [here](https://github.com/Horizontal-Labs/Argument-Mining/wiki/(Machine-Learning)-Models).


