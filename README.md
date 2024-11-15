# Knowledge Graphs for Retrieval-Augmented Generation (RAG)

![image](https://github.com/user-attachments/assets/c4b5d25e-ea62-4c15-b9f3-c03e75d8c356)

     
## Introduction    
      
This project explores the integration of **Knowledge Graphs** with Retrieval-Augmented Generation (RAG) to enhance the accuracy, relevance, and depth of generative AI systems. Knowledge Graphs structure information into entities (nodes) and relationships (edges), enabling efficient storage, querying, and reasoning. By leveraging Knowledge Graphs in RAG pipelines, the project demonstrates how to retrieve relevant, context-aware information and incorporate it into text generation.
    

## Key Areas Explored

### 1. Querying Knowledge Graphs     

Knowledge Graphs can be queried using **Cypher**, a powerful query language for interacting with graph databases such as Neo4j.  

- **Nodes** represent entities or concepts (e.g., companies, documents, or persons).  
- **Edges** denote relationships between entities (e.g., "owns," "reports to," or "mentions").  
- Queries extract specific nodes or paths, enabling targeted and meaningful retrievals.  

## 2. Preparing Text for RAG

- Text preparation is crucial to ensure accurate alignment between unstructured data and graph nodes. This involves:

- Entity Extraction: Identifying entities and their attributes from text.
- Relationship Mapping: Recognizing relationships between extracted entities.
- Data Cleaning: Preprocessing raw text to remove noise, normalize terms, and tokenize for structured representation.

## 3. Constructing a Knowledge Graph from Text Documents
Building a Knowledge Graph involves transforming unstructured text into a graph-based structure. The process includes:

- Text Ingestion: Loading text documents into the pipeline.
- Entity Recognition: Using tools to identify key entities.
- Graph Construction: Populating the graph database with nodes (entities) and edges (relationships).

## 4. Adding Relationships to SEC Knowledge Graph
The SEC Knowledge Graph aggregates data from the U.S. Securities and Exchange Commission filings to map:

- Companies to their officers, directors, and ownership structures.
- Financial reports and filing types to relevant entities.
- Relationships were added using:
  Named Entity Recognition (NER): To identify entities like "Company," "Director," and "Filing."
  Custom Scripts: To define relationships such as "Filed_By" or "Supervised_By."

## 5. Expanding the SEC Knowledge Graph
Expansion involved:

- Adding New Data: Incorporating additional filings, transactions, and relationships.
- Linking External Sources: Connecting SEC data with external datasets for richer insights.
- Automated Updates: Regularly updating the graph to reflect the latest filings.

## 6. Chatting with the Knowledge Graph
By integrating Neo4j with language models via LangChain_Community and OpenAI APIs, the project enables interactive querying of the graph. Users can ask natural language questions, which are translated into Cypher queries for execution against the Knowledge Graph.

Example:

User Query: "Who are the directors of Company A?"
Generated Cypher Query:
cypher
MATCH (c:Company)-[:HAS_DIRECTOR]->(d:Director)
WHERE c.name = "Company A"
RETURN d.name
The LLM interprets the results and generates a natural language response.
Core Concepts
1. Node
A Node represents an entity or concept in the graph. Each node can have attributes or properties, such as:

2. Cypher Query Language
Cypher is a declarative language for querying and manipulating graph data in Neo4j. It allows for expressive retrieval of graph patterns and relationships.


## 3. Retrieval-Augmented Generation (RAG)
RAG combines information retrieval with generative models to enhance responses. By querying Knowledge Graphs:

- Relevant context is retrieved efficiently.
- LLMs generate accurate and grounded answers.
- RAG Pipeline with Knowledge Graphs:

Input Query: The user asks a question.
Graph Query: The question is translated into a Cypher query to retrieve relevant data.
Response Generation: Retrieved data is used as input to an LLM for generating answers.

## Libraries and Tools Used
- langchain_community: To interact with Neo4j for querying and updating the Knowledge Graph.
- Neo4j: A graph database used to store and manage the Knowledge Graph.
- openai: For API-based interaction with language models to generate responses.
- pandas: For organizing and preprocessing text data.
- helpers: For utility functions like data cleaning and query conversion.

## Conclusion
This project demonstrates how Knowledge Graphs can enhance RAG pipelines, enabling precise and context-rich responses. By integrating structured data with generative models, this approach is applicable to various domains, including:

- Financial Analysis: Understanding complex relationships in SEC filings.
- Customer Support: Resolving queries using structured and unstructured knowledge.
- Enterprise Search: Enabling intelligent, context-aware search within organizational data.







 
