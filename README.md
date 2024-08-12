# RAGVectorDB_LLM_model
Combine RAG and Vector db (FAISS) with LLM model to extract relevant data from latest documents for a User Query

1.	Using a RAG model to Retrieve relevant documents from Vector db using similarity search for top k and Generating the output based on user query
2.	The output documents are then input along with the prompt to an LLM to perform desired action – extract data, summarize, etc
3.	The documents are first converted into tokenized embeddings from an LLM (Llama3-8B)
4.	The embeddings are then indexed in a vector Db (FAISS)
   o	The embeddings can also be written to any db like sqlite or cloud db
5.	The prompt query to the LLM is done via a text generation pipeline with the user prompt and the documents returned by the RAG model
6.	Example: simple list of health and auto insurance claims data with key value comma separated data as documents
   o	It contains claimant, claim amount, paid amount
7.	This document list is converted to embeddings and then queried via RAG
8.	Results of RAG are used to prompt LLM to return just the claim $ amount
9.	Python code notebook is given in github - 

•	This is a simple model to show end to end process and can be extended to larger data sets and more complex queries
•	Benefit of using RAG model is that there is no need to fine-tune or re-train and LLM which is resource intensive and the LLM’s generally lack latest information
•	This allows using the benefits of LLM functionality while using latest information stored in a database as documents, ensuring recency and relevance
•	Users can query the latest data to extract contextually relevant information
•	Langchain can then be used to chain together multiple LLM prompts to get more accurate results

