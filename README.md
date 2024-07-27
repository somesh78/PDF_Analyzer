# PDF Chatbot

## Overview

The PDF Chatbot is a Streamlit application that allows users to interact with PDF documents. Users can upload multiple PDF files, and the chatbot uses Google Generative AI to answer questions based on the content of the uploaded documents. The application utilizes Langchain for processing text and managing conversational interactions.

## Features

- Upload multiple PDF files and extract text from them.
- Split extracted text into manageable chunks.
- Use a vector store (FAISS) to enable fast similarity searches.
- Ask questions about the content of the uploaded PDFs, with context-based responses.

## Requirements

- Python 3.7 or higher
- Streamlit
- Langchain
- PyPDF2
- dotenv
- langchain-google-genai
- langchain-community

## Installation

1. Install the required packages : `pip install -r requirements.txt`

2. Create a .env file in the root of the project and add your Google API key : `GOOGLE_API_KEY=your_google_api_key_here`

## Usage

1. Run the streamlit app : `streamlit run app.py`

2. Open your web browser and go to http://localhost:8501.

3. Use the sidebar to upload one or more PDF files.

4. After uploading, enter your questions in the text input field and press Enter. The chatbot will respond with answers based on the content of the PDFs.

## Code Structure

- app.py: Main application file containing the logic for handling PDF uploads, text extraction, chunking, vector store creation, and user interaction.

## Key Functions

- get_pdf_reader(pdf_docs): Reads the uploaded PDF files and extracts text.
- get_text_chunks(text): Splits the extracted text into manageable chunks for processing.
- get_vector_store(text_chunks): Creates a FAISS vector store from the text chunks for efficient searching.
- get_conversational_chain(): Initializes the QA chain using Google Generative AI.
- load_faiss_index(pickle_file): Loads the FAISS index for similarity search.
- user_input(user_question): Processes user questions, searches for similar documents, and provides responses.