# LLM Chain Prompting and Retrieval-Augmented Generation QA with GPT-3.5
## Here are two implementations of OpenAI's GPT-3.5 for personal/business use cases.
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

# Deploying LangChain on Streamlit and Gradio

## For streamlit, I developed a chatbot that uses the same model as in the notebook. I have deployed two variations of the chatbot: one to ingest an online article url and the other to ingest csv data. I have also added the option to upload your own csv data and have GPT answer questions regarding your dataset. 
### 1. Article Search QA chatbot
### For the article, I uploaded the same iOS 17 article. The benefit of using a chatbot is remembering conversation history as context for better understanding and giving additional context. I asked it questions regarding the new features in iOS 17 and it was successfully able to summarize the article in a bulletpoint format. It was also able to successfully return the new messaging features in iOS 17 and give a detailed description on the new Live Stickers feature.
![Alt text](/Screenshots/urlchatbot.png?raw=true "url1")
### 2. CSV QA chatbot
### For this article, I have loaded my own personal data on a game mode in League of Legends called ARAM that I play with my friends. We have a group of 5 people and this csv file has statistics on champion (the in-game character) metrics for each person in our group. The metrics that are measured are win %, games played, wins, losses, KDA ((kills + assists)/deaths), kills, deaths, assists, etc. Through loading this csv data into the chatbot, I can ask it questions regarding the metrics I'm interested in. I can easily see who is better at a specific champion amongst my friends.
![Alt text](/Screenshots/csvchatbot1.png?raw=true "csv1")
![Alt text](/Screenshots/csvchatbot2.png?raw=true "csv2")



## For gradio, I uploaded the chain prompt of summarizing and translating movie reviews to a user friendly interface. Users can easily submit input text (doesn't have to be a movie review) and the chatbot should summarize it and then translate that summary to French. 
![Alt text](/Screenshots/gradiomoviereviews.png?raw=true "gradio")

