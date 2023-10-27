# LLM Chain Prompting and Document Search QA
## Here are two implementations of OpenAI's ChatGPT for personal/business use cases.
## 1. Utilizing LangChain to answer questions regarding the iPhone's new software update iOS 17. 
### The process is called Retrieval-Augmented Generation or RAG. You can't directly feed the input text into a prompt as it takes up too many tokens. Rather through utilization of Langchain and OpenAI embeddings, we can embed the document into vectors. Before that, we need to split the document into chunks and then through semantic similarity we retrieve the chunk with the similar embeddings.
#### **Pipeline Process**
#### Loading: First we need to load our data. Use the LangChain integration hub to browse the full set of loaders.
#### Splitting: Text splitters break Documents into splits of specified size
#### Storage: Storage (e.g., often a vectorstore) will house and often embed the splits
#### Retrieval: The app retrieves splits from storage (e.g., often with similar embeddings to the input question)
#### Generation: An LLM produces an answer using a prompt that includes the question and the retrieved data
## 2. Utilizing LangChain to create a Chain prompt with a two step process for translating and summarizing movie reviews
### With Langchain, you can chain prompt. Chain prompting is utilizing the output from a previous prompt and taking that as input for the next step in the chain process. For this project, I'm going to have ChatGPT summarize a movie review in less than 10 words and then translate that summary into French.
#### **Pipeline Process**
#### Loading: The dataset is loaded in using pandas read_csv.
#### Creating the chain: The first prompt takes in the input and then summarizes the review in less than 10 words. The second prompt translates that summary into French. 
#### Generation: An LLM produces an answer using a prompt that includes the question and the retrieved data and the same LLM uses that previous response to generate a new response.
