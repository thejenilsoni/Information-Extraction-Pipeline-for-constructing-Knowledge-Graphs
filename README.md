# Constructing Knowledge Graphs from Unstructured Text

This project demonstrates how to automatically construct a knowledge graph from unstructured text using large language models (LLMs), Wikipedia data, and a Neo4j graph database. The workflow is implemented in a Jupyter notebook and leverages the LangChain framework for information extraction and graph operations.

## Features
- **Automated Extraction**: Uses OpenAI's GPT-4o to extract entities and relationships from Wikipedia articles.
- **Structured Output**: Enforces strict rules for node and relationship labeling, property formatting, and coreference resolution.
- **Graph Database Integration**: Stores the extracted knowledge graph in a Neo4j database for advanced querying.
- **Natural Language QA**: Enables natural language question answering over the constructed graph using Cypher queries.

## Workflow Overview
1. **Install Dependencies**: Installs all required Python packages (LangChain, Wikipedia loader, OpenAI, Neo4j, etc.).
2. **Connect to Neo4j**: Sets up a secure connection to a Neo4j Aura instance using credentials.
3. **Define Data Models**: Uses Pydantic to define models for nodes, relationships, and the overall knowledge graph.
4. **Extraction Chain**: Configures a prompt and LLM chain to extract structured graph data from text.
5. **Load and Split Documents**: Loads Wikipedia articles and splits them into manageable chunks.
6. **Extract and Store**: Processes each chunk, extracts entities/relationships, and stores them in Neo4j.
7. **Query the Graph**: Uses LangChain's Cypher QA chain to answer questions about the graph in natural language.

## Requirements
- Python 3.8+
- Access to [Neo4j Aura](https://neo4j.com/cloud/aura/)
- OpenAI API key (GPT-4o or compatible model)

## Setup Instructions
1. **Clone the Repository**
   ```sh
   git clone https://github.com/thejenilsoni/Information-Extraction-Pipeline-for-constructing-Knowledge-Graphs.git
   cd Information-Extraction-Pipeline-for-constructing-Knowledge-Graphs
   ```
2. **Install Dependencies**
   Run the first cell in the notebook or manually install:
   ```sh
   pip install langchain langchain_community wikipedia tiktoken langchain-openai langchain-neo4j
   ```
3. **Configure Credentials**
   - Set your Neo4j Aura connection details and OpenAI API key. The notebook expects these via `google.colab.userdata` (for Colab) or you can modify the code to use environment variables.

4. **Run the Notebook**
   Open `extraction_pipeline.ipynb` and execute the cells in order.

## Usage
- The notebook will load Wikipedia data (default: "Walt Disney"), extract a knowledge graph, and store it in Neo4j.
- You can modify the query or allowed node types as needed.
- Use the QA cells at the end to ask questions about the constructed graph.

## Customization
- **Change Data Source**: Edit the Wikipedia query to extract knowledge graphs for other topics.
- **Restrict Node Types**: Adjust the `allowed_nodes` list to control which entity types are extracted.
- **Extend Extraction Rules**: Modify the prompt in the extraction chain for different graph construction rules.

## License
This project is for educational and research purposes. See LICENSE for details.

## Acknowledgments
- [LangChain](https://github.com/langchain-ai/langchain)
- [Neo4j Aura](https://neo4j.com/cloud/aura/)
- [OpenAI](https://openai.com/)
