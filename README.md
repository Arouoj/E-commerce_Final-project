# E-commerce_Final-project

## Project Overview

This project is an AI-powered e-commerce chatbot that interacts with a structured SQL database of products to answer user queries. The chatbot is built using LangChain and Groq's LLM API, enabling intelligent SQL query generation and execution. It is implemented in Python and runs in Google Colab with persistent data storage via Google Drive.

## Features

- **Interactive Chatbot**: Allows users to query the product database in natural language.
- **SQL Database Integration**: Uses SQLite for database management.
- **LLM-based Query Generation**: Employs LangChain and Groq's LLM for translating natural language queries into SQL.
- **Automated Database Initialization**: Populates the database with sample product data.
- **Error Handling**: Implements query cleaning and exception handling for robustness.

## Setup & Installation

1. Clone the repository or download the notebook file.
2. Open the notebook in Google Colab.
3. Install the required dependencies:
   ```python
   !pip install -qU langchain-groq langchain-community
   ```
4. Mount Google Drive for persistent storage:
   ```python
   from google.colab import drive
   drive.mount('/content/drive')
   ```
5. Run the notebook to initialize the database and start the chatbot.

## Code Structure

### 1. Database Management
- **`Product` Model**: Defines the schema for storing product data.
- **`initialize_database()`**: Creates the database and inserts sample product records.

### 2. Query Processing
- **`clean_sql_query(query: str) -> str`**: Cleans and formats generated SQL queries.
- **`execute_query(db, query) -> list`**: Executes SQL queries and returns results.
- **`chat_with_sql(chain, db, query) -> str`**: Processes user queries, generates SQL, and executes it.

### 3. Chatbot Execution
- **`setup_chatbot()`**: Initializes the LLM and connects it to the SQL database.
- **`start_chatbot()`**: Provides an interactive CLI-based chatbot experience.

## Example Queries

Users can ask:
- "What is the cheapest product?"
- "Show me top-rated electronics products."
- "How many products does the company sell, and how many are in stock?"
- "What products cost less than $50? Provide names, prices, and ratings."
- "What are the top-rated brands, and what are their average prices?"

## Future Improvements
- Add a web-based UI for user interaction.
- Enhance query understanding with improved LLM fine-tuning.
- Expand product database with real-time updates.
- Implement a caching mechanism for frequently asked queries.

## License
This project is open-source and available for modification and distribution under the MIT License.

