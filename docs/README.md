# Text Mining Project – 2023/24

**Group W_Team**

**Supervisor**: Prof. Flora Amato  

> [!WARNING]
> The following text is taken from the [official Italian documentation](./doc_ITA.pdf), translated and rewritten thanks to generative IA. It may therefore contain inaccuracies.

Table of contents
=================

<!--ts-->
- [Text Mining Project – 2023/24](#text-mining-project--202324)
- [Table of contents](#table-of-contents)
  - [Introduction](#introduction)
  - [Principle of Operation](#principle-of-operation)
  - [Code Explanation](#code-explanation)
  - [Functional Blocks](#functional-blocks)
  - [Flow Diagram](#flow-diagram)
  - [Implementation](#implementation)
<!--te-->
  
## Introduction
A chatbot is software designed to simulate conversations with human users, using natural language. They are now part of everyday life, such as in any Customer Service that can answer frequently asked questions. The operation of a chatbot is comparable to an if-else cycle, with predefined rules and keyword matching.

Early chatbots were quite static, based on a database of predefined responses. Essentially, a user would input a query, the chatbot would look up the rules associated with the question, and provide the associated response. Modern chatbots are based on large language models (LLMs), offering more advanced interactions and dynamism. There are two types:

1. **RAG-based chatbots:** Combine retrieval methods and generative AI to provide accurate and contextually relevant responses.
2. **LLM-based chatbots without RAG:** Utilize large datasets and models like OpenAI or Llama, handling a wide range of questions without predefined rules but requiring high computational power.

The chatbot developed in this project is RAG-based and is illustrated in the next chapter.

## Principle of Operation
The RAG chatbot takes a collection of files (PDFs) as input and provides answers based on the context provided by the files. The process involves:

1. **Document Processing:** Input documents are divided into small chunks and converted into embedding vectors to capture semantic meaning.
2. **Storage:** These vectors are stored in a database optimized for rapid and accurate information retrieval.
3. **Question Handling:** When a question is posed, it is converted into an embedding vector, and similar chunks are retrieved from the database.
4. **Response Generation:** The retrieved chunks are passed to an LLM to generate the final response, which is then sent to the user and saved in the history.

## Code Explanation
The programming environment used was Google Colab. The code is structured in 10 main regions:

1. **Installation of necessary packages and libraries** like Gradio, Pydfd, and Transformers.
2. **Importing a pre-trained and multilingual model** based on Llama-3-8b-instruct.
3. **Loading a quantized model** to reduce resource consumption.
4. **Creating an API key on Google Colab** and connecting to Google Drive.
5. **Importing documents** from the 'document_colab' folder in Google Drive.
6. **Text chunking** for efficient information retrieval.
7. **Preparing a multilingual embedding model**.
8. **Creating a Retrieval-Generation system** for responding to user questions.
9. **Creating the conversation interface** using Gradio.

## Functional Blocks
The chatbot consists of several functional blocks, each performing a specific task:

1. **Vector Database:** Created using ChromaDB, optimized for high-speed vector operations.
2. **Langchain:** Framework to integrate LLM models, handle document processing, and manage conversations.
3. **Embedding:** Using the model paraphrase-multilingual-MiniLM-L12-v2 from HuggingFace.
4. **Gradio:** For creating a web user interface.

## Flow Diagram
To run the chatbot correctly, follow these steps:
1. Create a 'documents_colab' folder in your Google Drive.
2. Import PDF documents into this folder.
3. Open the code on GitHub and check if the selected GPU is T4. If not, change it.
4. Add a Hugging Face API key as a secret in Google Colab.
5. Run the code and use the Gradio interface to interact with the chatbot.

## Implementation
Two main components were used for implementation: GitHub and Google Colab. GitHub for code management and versioning, and Google Colab for an interactive, shareable coding environment.

- **GitHub:** Offers version control, collaboration tools, and project management integration.
- **Google Colab:** Provides an interactive environment with preconfigured libraries, high-performance computing support, and Google Drive integration.

The goal was to create an entirely open-source project accessible and modifiable by anyone.


