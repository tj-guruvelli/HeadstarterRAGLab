# HeadstarterRAGLab


## OVERVIEW

Retrieval-Augmented Generation (RAG) is a technique primarily used in GenAI applications to improve the quality and accuracy of generated text by LLMs by combining two key processes: retrieval and generation.

### Breaking It Down:
## Retrieval:
Before generating a response, the system first looks up relevant information from a large database or knowledge base. This is like searching through a library or the internet to find the most useful facts, articles, or data related to the question or topic.
## Generation:
Once the relevant information is retrieved, the system then uses it to help generate a response. This is where the model, like GPT, creates new text (answers, explanations, etc.) based on the retrieved information.
Using PINECONE and GROQ as open-source tools for demonstration and accessibility


### Initialize the HuggingFace Embeddings client
- Can use OpenAI Embedding model, or others like NVIDIA if you want to experiment other than HuggingFace.
- Converts text into numbers Retains its semantic meaning


### Initialize the Groq client
Free Llama 3.1 API via Groq
```groq_client = Groq(api_key=os.getenv('GROQ_API_KEY'))```


### Calculating sentence similarity with embeddings
- Only need to be pulling from relevant documents and not all the documents or info that an company might have on internal data, SO we need a way to define WHICH documents are relevant
- The sentences produced here are basically the sentences in matrix form like in linear algebra


### Load in the Data
- Learn more about the dataset [here](https://www.google.com/url?q=https%3A%2F%2Fwww.kaggle.com%2Fdatasets%2Fayoubcherguelaine%2Fcompany-documents-dataset)

### Initialize Pinecone
- It takes a few minutes to intialize
- Way to parition data together
- Split different comapnies into different NAMESPACES


### Insert data into Pinecone
- This prints out the documents strutcures
- 'File' is the path to data files
- 'Data' is the actual content in the file
- Way to represent pdfs and extracted text
