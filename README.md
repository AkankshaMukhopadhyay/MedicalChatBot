End-to-End Medical Chatbot with Llama 2

This project demonstrates an end-to-end Retrieval-Augmented Generation (RAG) medical chatbot built using Llama 2, LangChain, Pinecone, and Flask. The chatbot answers questions based on documents loaded into a Pinecone vector database.

🚀 Tech Stack

Python: The core programming language.

LangChain: Framework for building LLM applications.

Flask: Web framework for the user interface.

Meta Llama 2: The Large Language Model used for generation (specifically llama-2-7b-chat.ggmlv3.q4_0.bin).

Pinecone: Vector database for storing and retrieving document embeddings.

⚙️ Setup and Installation

Follow these steps to set up and run the project locally.

Prerequisites

Conda: Ensure you have Conda installed to manage environments.

Step 1: Clone the Repository

Clone this project to your local machine:

git clone <YOUR_REPOSITORY_URL_HERE>
cd <YOUR_REPOSITORY_FOLDER_NAME>


(Replace <YOUR_REPOSITORY_URL_HERE> and <YOUR_REPOSITORY_FOLDER_NAME> with your actual repo details)

Step 2: Create and Activate Conda Environment

Create a dedicated Conda environment using Python 3.8:

conda create -n mchatbot python=3.8 -y
conda activate mchatbot


Step 3: Install Dependencies

Install the required Python packages:

pip install -r requirements.txt


Step 4: Configure Pinecone Credentials

Create a file named .env in the root directory of the project.

Add your Pinecone API key and environment name to the .env file:

PINECONE_API_KEY="YOUR_ACTUAL_PINECONE_API_KEY"
PINECONE_API_ENV="YOUR_ACTUAL_PINECONE_ENVIRONMENT"


Step 5: Download Llama 2 Model

Download the quantized Llama 2 model file: llama-2-7b-chat.ggmlv3.q4_0.bin

Get it from the official source: TheBloke/Llama-2-7B-Chat-GGML (Look for the specific file in the "Files and versions" tab).

Create a folder named model in the project's root directory (if it doesn't exist).

Place the downloaded .bin file inside the model directory.

▶️ Running the Application

Step 1: Load Data into Pinecone

Run the store_index.py script to process your documents (assuming they are in a data/ folder) and load their embeddings into your Pinecone index.

python store_index.py


(This step only needs to be run once, or whenever your source documents change)

Step 2: Start the Chatbot Application

Run the app.py script to start the Flask web server:

python app.py


Step 3: Access the Chatbot

Wait for the terminal to indicate the server is running (usually on http://127.0.0.1:8080 or http://0.0.0.0:8080).

Open your web browser and navigate to the displayed localhost address (e.g., http://127.0.0.1:8080).

You should see the chatbot interface and can start asking questions! 🎉
