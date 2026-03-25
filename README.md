🍳 Indonesian Cuisine RAG-Assistant
This project is a Retrieval-Augmented Generation (RAG) system designed to provide an intelligent Q&A assistant for Indonesian food recipes. By combining the power of LangChain, FAISS, and Google Gemini API, this assistant delivers accurate answers including ingredients, cooking steps, and direct source references from the dataset.

🌟 Key Features
Semantic Search: Unlike traditional keyword search, this system understands the context of your question using HuggingFace embedding models.

Hallucination Reduction: By using a specific dataset of 14,000+ Indonesian recipes, the AI is grounded in real data, significantly reducing "made-up" information.

Structured Tutorials: Provides clear, numbered cooking instructions and bulleted ingredient lists.

Source Transparency: Every response includes the original Cookpad URL for verification and further reading.

Robust Model Handling: Features a multi-model initialization script to handle various versions of the Gemini API (Flash/Pro) seamlessly.

🛠️ Tech Stack
Framework: LangChain

LLM: Google Gemini 2.5 Flash

Vector Database: FAISS (Facebook AI Similarity Search)

Embeddings: sentence-transformers/all-MiniLM-L6-v2

Data Analysis: Pandas & NumPy

Environment: Kaggle / Google Colab

📊 Dataset
The dataset is sourced from Kaggle, containing over 14,000 authentic Indonesian recipes. Each record includes:

Title: The name of the dish.

Ingredients: Detailed list of items needed.

Steps: Chronological cooking instructions.

Loves: Popularity metric from Cookpad.

URL: Direct link to the original recipe.

🚀 How It Works
Ingestion: The CSV dataset is processed into LangChain Document objects.

Indexing: Recipe text is converted into mathematical vectors (embeddings) and stored in the FAISS vector store.

Retrieval: When a user asks a question, the system retrieves the top 3 most relevant recipes based on semantic similarity.

Augmentation: The retrieved recipes are fed into a specialized Prompt Template.

Generation: The Gemini LLM generates a friendly, professional chef-like response based only on the provided context.

📂 Project Structure
initialize_llm(): Logic to authenticate and select the best available Gemini model.

format_docs_with_metadata(): Custom processor to inject URLs and Titles into the AI's context.

rag_chain: The core LCEL (LangChain Expression Language) pipeline connecting the retriever, prompt, and LLM.

📝 Example Usage
User Query: "How do I make Bakwan Ayam?"

Assistant Output:

"Hello, food enthusiasts! To make crispy and savory Bakwan Ayam, you will need... [Ingredients List]... Here are the steps... [Tutorial]... Source: https://cookpad.com/id/resep/4312352-bakwan-ayam"
