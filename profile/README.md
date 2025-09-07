### Quick Access:
* [Project Description](#argument-mining---uncovering-the-structure-of-persuasion-in-diverse-media)
* [Pipeline Overview](#c4-model---pipeline-overview)
* [Repositories](#repositories)
* [Pipeline Setup Guide](#pipeline-setup-guide)

---
# Argument Mining – Uncovering the Structure of Persuasion in Diverse Media  

This project explores how arguments are formed and expressed in everyday communication. By building tools that automatically detect claims, premises, and their relationships, we aim to make debates, online discussions, and political discourse easier to follow and analyze.  

The core idea is simple: given a piece of text, our pipeline identifies argumentative units (ADUs) and shows how they connect to form reasoning. To make these structures easier to understand, we provide a **graph visualization** that highlights how claims are supported or opposed by premises, and whether they take a *pro* or *con* stance.  

Along the way, we also tested various open-source language models and investigated whether fine-tuning them with argumentative data collected from the internet could improve results. Details of this work are documented [here](https://github.com/Horizontal-Labs/training-zoo/wiki/Fine-Tuning-Datasets)

Our open-source implementation is designed for practical use across different domains, from legal texts and policy discussions to social media analysis. The outcome is a working prototype that can process real-world data and present argument structures in a clear, visual format.  

---
# C4 Model - Pipeline Overview
<img width="2314" height="1000" alt="image" src="https://github.com/user-attachments/assets/eb366506-e78a-49d5-909d-2a1458c6af77" />

Our Argument Mining pipeline connects a frontend web application with a backend API and a set of machine learning models to process text into structured argumentative graphs.  

1. **Client Access**  
   Users interact with the system by visiting the web application in their browser. The app is served as a Single Page Application (SPA) and runs entirely in the client’s browser.  

2. **Web Server**  
   The SPA (built with Vue/TypeScript) is delivered as static files (HTML, CSS, JS) by a web server such as NGINX or Apache.  

3. **Frontend (SPA)**  
   The SPA handles user input (e.g., free text or documents) and communicates with the backend API. It then displays an **interactive graph** where argumentative discourse units (ADUs: claims and premises) are shown along with their relationships (supports or opposes).  

4. **API Service**  
   The backend API (built with Python/FastAPI or Flask) exposes HTTP endpoints for text processing. It receives dialogue data from the frontend, orchestrates model inference, manages requests, and returns structured graph data in JSON.  

5. **Machine Learning Models**  
   The API loads and executes pre-trained or fine-tuned NLP models (e.g., BERT-based) that detect claims, premises, and stance relationships. The output is structured graph data that can be rendered by the frontend.  

In short:  
The **frontend** collects user input and renders argument graphs → the **API** coordinates requests and processing → the **ML models** analyze the text and provide structured argumentative data.  

---
# Repositories

Our project involved the creation of eight repositories. The following two are crucial for reproducing our pipeline and therefore more in detail explained both in this README ([Pipeline Setup Guide](#pipeline-setup-guide)) and in their repository wikis:
* **[armin-app](https://github.com/Horizontal-Labs/armin-app/wiki)**: This repository houses the web frontend, built using Vue.
* **[argument-mining-api](https://github.com/Horizontal-Labs/argument-mining-api/wiki)**: Boots up the argument mining models and provides API endpoints to feed text into them. It delivers ADUs (Claims, Premises) and the Stance Relationships between those as a result.

In addition, we developed other repositories for developing and testing purposes:

* **[training-zoo](https://github.com/Horizontal-Labs/training-zoo/wiki)**: Dedicated to training our decoder and encoder models.
* **[synapse-sparks](https://github.com/Horizontal-Labs/synapse-sparks/wiki)**: Here, we tested and engineered prompts for Large Language Models.
* **[benchmark](https://github.com/Horizontal-Labs/benchmark/wiki)**: Contains the benchmark data used to compare the results of our models.
* **[prototype-pipeline](https://github.com/Horizontal-Labs/prototype-pipeline/wiki)**: Holds our initial pipeline implementation, which was replaced by a more effective solution.
* **[argument-mining-db](https://github.com/Horizontal-Labs/argument-mining-db/wiki)**: This repository hosts our MariaDB database which was used for storing our training data.
* **[prototype-graph-visualization](https://github.com/Horizontal-Labs/prototype-graph-visualization/wiki)**: Contains testing of graph visualization.
---
# Pipeline Setup Guide

To run our Argument Mining pipeline, we created this step-by-step manual to guide you through it. 

## Step 1: Setup the Backend
To begin, you'll want to set up the **[argument-mining-api](https://github.com/Horizontal-Labs/argument-mining-api/wiki)** repository. This repository contains the core logic, models, and API endpoints.

## Step 2: Setup the Frontend
Once the API Server is setup and running, you can begin setting up the frontend using the **[armin-app](https://github.com/Horizontal-Labs/armin-app/wiki)** repository. It connects to the endpoints from the argument-mining-api and provides a simpler interface to use the pre-trained models or different versions of OpenAI’s GPT models.

## Step 3: Mine Arguments! 😄

