# Medi 1.0 
Medi is an RAG based AI Assistant, which is targeted for medical questions. 
## How to run?
### STEPS:

Clone the repository

```bash
git clone https://github.com/Mebrie-Awoke/Complete_medicalChatbot
```



### STEP 02- install the requirements
```bash
pip install -r requirements.txt
```


### Create a `.env` file in the root directory and add your groq Api Key as follows:

```ini

GROQ_API_KEY = "xxxxxxxxxxxxxxxxxxxxxxxxxxxxx"
```


```bash
# run the following command to store embeddings to chromadb
python index.py
```

```bash
# Finally run the following command
python app.py
```

Now,
```bash
open up localhost:
```


### Techstack Used:

- Python
- LangChain
- Flask
- GROQ
- Chromadb


	

