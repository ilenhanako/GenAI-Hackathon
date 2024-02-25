# Frequently Asked Questions (Technical)

Question: Which Large Language Model (LLM) API is provided?

Answer: `gpt-35-turbo-16k` from Microsoft Azure OpenAI (not OpenAI)

---

Question: What is the maximum token length allowed for this model provided?

Answer: As the name suggests it should allow for ~16,000 tokens. The exact details can be found at https://learn.microsoft.com/en-us/azure/ai-services/openai/concepts/models#public-cloud-regions-1

---

Question: What is the difference between Azure OpenAI and Open AI API? Are they the same?

Answer: Azure OpenAI is the enterprise version of the OpenAI APIs, which has the data tenanted to Temasek’s tenant. Functionality-wise, the APIs are similar.

---

Question: Can we request for other models like `gpt-4`, `gpt-4 (vision-preview)`, `dalle2` or `dalle3`? Can we request for embeddings API like the `text-embedding-ada-002`?

Answer: For the most part, the provided LLM API should suffice, we recommend teams to use that.For embeddings, you can use local models (ie those from HuggingFace) to generate them. See https://bitbucket.org/hackathon-genai/genai-starter-kit/src/master/pages/05_%F0%9F%94%8D_qna_with_rag.py for an example. If you really need other models, the request will be granted on an ad-hoc basis, and it will be on the hackathon team to ensure that the spent amount does not burst the daily budget.

---

Question; Must we only use the API provided? Can we use run local models like Llama2 or Mistral?

Answer: The use of the Azure OpenAI API is recommended.

---

Question: Are there any limits or quota for the API usage?

Answer: Each team should be using up to a **maximum limit of 20M tokens per day** for `gpt-35-turbo-16k` - which translates to about **SGD100 per team per day**

---

Question: How do I keep track of my API usage? Must we use Python utils functions to make AzureOpenAI API calls?

Answer: AzureOpenAI API calls can be made by wrapper function provided in genai-starter-kit utils module
- this way, every single call is logged and saved locally for participants reference (total tokens and cost)
Alternatively, participants can opt not to use the wrapper function and use the API directly
- however participants will have to track usage on their own voluntarily if they are concerned that they might exceed the quota limit
**Regardless, usage will be tracked and monitored automatically on our end**, regardless of whether participants use use the wrapper functions to log and track the usage.  
- Daily usage updates will be provided for all.

---

Question: How do I get started to build a GenAI prototype for the hackathon? Where can I find the genai-starter-kit?

Answer: Git clone from https://bitbucket.org/hackathon-genai/genai-starter-kit and run the sample app. Then you can either modify from that repo or git fork a new one.

---

Question: Where are we supposed to run and host our prototype? Can I host the prototype online?

Answer: Please host your prototype on your local laptop.

---

Question:Must we push our codes to Bitbucket? Can we push our codes in GitHub?

Answer: Yes, please push your code to the same Temasek Bitbucket workspace to collaborate between your team members. You should not push your code into other public repository like Github or Gitlab.

---

Question: Must I only use Streamlit and follow the genai-starter-kit to build our prototype?

Answer: No, it is not compulsory to use Streamlit or follow the genai-starter-kit to build your prototype. You can also use other alternatives like Gradio, Chainlit or build your own custom frontend and backend services with other framework/languages. 

---

Question: Can I use LangChain?

Answer: Yes, in fact the genai-starter-kit uses the latest version of LangChain, although only selectively for certain parts. Just be aware you might lose some features provided by the utils wrapper function if you opt to use the LangChain end to end. Note that, there are components of LangChain that relies on external online service (e.g. LangSmith); those should not be used.

---

Question: Can I use LlamaIndex

Answer: Yes, but since LlamaIndex also provides its own wrapper functions and classes, you’ll be on your own. The same Azure OpenAI credentials and environment variables should still work.

---

Question: What kind of vector stores can I use to implement RAG? Can I use Pinecone, ChromaDB, Qdrant, Weavite, Milvue or FAISS?

Answer: The rule of thumb is you should be running the entire prototype locally, and only make external API calls to Azure OpenAI. Since Pinecone is a cloud-based vector database, it shouldn't be used. Qdrant, ChromeDB and Weaviate, Milvus and other similar databases can be used only if you run them locally. A very basic example of FAISS as local vector store is provided in the starter-kit.

---

Question: Can I implement a live web scraping in my prototype to gather data?

Answer: As the theme of the hackathon is generative AI, we recommend that teams work on the generative AI / machine learning portions of the project first. This means that project teams should gather the data required for the project before the 1st day of the hackathon. We suggest to implement the web scraping portion only if you have additional time.