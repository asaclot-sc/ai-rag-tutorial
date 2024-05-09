# rag-tutorial-v2


pypdf
langchain
langchain_community
chromadb # Vector storage
pytest

Install:
`pip install -r requirements.txt`

ollama

ollama pull llama2

ollama pull nomic-embed-text


https://github.com/pixegami/rag-tutorial-v2

https://blogs.nvidia.com/blog/what-is-retrieval-augmented-generation/
https://research.ibm.com/blog/retrieval-augmented-generation-RAG
https://blog.langchain.dev/tutorial-chatgpt-over-your-data/


The Rise and Potential of Large Language Model Based Agents: A Survey
https://arxiv.org/pdf/2309.07864

https://arxiv.org/pdf/2005.11401
Retrieval-Augmented Generation for Knowledge-Intensive NLP Tasks

https://llama.meta.com/llama2/

https://github.com/ollama/ollama


https://huggingface.co/nomic-ai/nomic-embed-text-v1.5
https://blog.nomic.ai/posts/nomic-embed-text-v1

https://static.nomic.ai/reports/2024_Nomic_Embed_Text_Technical_Report.pdf
Nomic Embed: Training a Reproducible Long Context Text Embedder

https://arxiv.org/abs/2205.13147
Matryoshka Representation Learning

https://docs.trychroma.com/



`python populate_database.py --reset`

`python query_data.py "What are the card types in Ticket to Ride?"`


Example embedding using Bedrock:

```
from langchain_community.embeddings.bedrock import BedrockEmbeddings

def get_embedding_function():
    embeddings = BedrockEmbeddings(
        credentials_profile_name="default", region_name="us-east-1"
    )
    return embeddings

```