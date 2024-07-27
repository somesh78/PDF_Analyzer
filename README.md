# PDF Chatbot

A Streamlit application that allows users to upload PDF files, analyze the content, and interact with the documents through a conversational chatbot. The application utilizes Google Generative AI for embeddings and conversation, FAISS for vector storage, and PyPDF2 for PDF parsing.

## Features

- Upload multiple PDF files.
- Extract text from the uploaded PDFs.
- Split the extracted text into manageable chunks.
- Create and store a vector representation of the text using FAISS.
- Conversational AI interface to interact with the content of the PDFs.

## Prerequisites

- Python 3.10+
- Google API Key for Generative AI

## Installation

1. Clone the repository:
    ```bash
    git clone https://github.com/yourusername/pdf-chatbot.git
    cd pdf-chatbot
    ```

2. Create and activate a virtual environment:
    ```bash
    python -m venv venv
    source venv/bin/activate  # On Windows, use `venv\Scripts\activate`
    ```

3. Install the required packages:
    ```bash
    pip install -r requirements.txt
    ```

4. Set up environment variables:
    Create a `.env` file in the root directory and add your Google API key:
    ```plaintext
    GOOGLE_API_KEY=your_google_api_key
    ```

## Usage

1. Run the Streamlit application:
    ```bash
    streamlit run app.py
    ```

2. Open your web browser and navigate to `http://localhost:8501`.

3. Use the sidebar to upload PDF files.

4. Click the "Submit" button to process the PDFs and create the vector store.

5. Enter your questions in the input box to chat with the extracted content from the PDFs.

## Code Overview

- `app.py`: Main application script.
    - Handles file uploads, text extraction, text chunking, vector store creation, and user interaction.
    - Defines the structure of the Streamlit application.
  
- `requirements.txt`: List of required Python packages.

## Functions

- `get_pdf_reader(pdf_docs)`: Reads the uploaded PDF files and extracts text.
- `get_text_chunks(text)`: Splits the extracted text into manageable chunks.
- `get_vector_store(text_chunks)`: Creates a vector store from the text chunks using FAISS and saves it locally.
- `get_conversational_chain()`: Creates a conversational chain using Google Generative AI.
- `load_faiss_index(pickle_file)`: Loads the FAISS index from a local file.
- `user_input(user_question)`: Processes the user's input question and displays the response.

## Security Notice

The deserialization of FAISS index involves a potential security risk. Ensure you trust the source of the FAISS index file. The `allow_dangerous_deserialization=True` flag is set in the `load_faiss_index` function to handle this.



https://github.com/user-attachments/assets/22ea18e1-bbb7-4dc2-8ba5-253e85847c3b


