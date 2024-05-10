# Workshop

## What problems are we solving?

- Query our own data sources (PDFs)
- Data is private
- All AI processes must be local
- Guarantee data is not used for training

## Introducing local LLMs

- Many you have heard of before:
- `llama`, `mistral`, `codellama`
- Download and query it locally

## How do we query an LLM locally?

- Ollama is your friend
- Download and install it - https://ollama.com/download
- Written in Go (just a fun fact)
- Let's us pull different models from the cloud - `ollama pull llama3`
- Runs as a local server and provides an API
- Install the CLI to query the server - `ollama run llama3 "why is water wet?"`
- There's plenty you can do with it - https://github.com/ollama/ollama

## How do I build LLM applications locally?

- LLM frameworks like `langchain` make this possible
- We'll use `langchain` because it is easy and fast to get started
- `langchain` is a Python framework
- `lanchain_community` are 3rd party integrations
- Install it - `pip install langchain langchain_community`

## So how does this LLM interact with documents?

- We're going to use a techique called Retrieval Augmented Generation (RAG)
- We read and chunk documents into a vector database
- We can retreive document chucks that are "similar" text in a query
- These chunks are then used to contextualise a prompt for our LLM
- `chroma` is a vector database we can run locally - https://www.trychroma.com/
- The `langchain` framework can talk to `chroma` and retrive context for the LLM, in our case `llama3`
- Install it - `pip install chromadb`

## How do I read PDFs with Python?
- We need to read our folder of PDFs, with the help of a library
- Install it - `pip install pypdf`
- Now we can use the `langchain.document_loaders.pdf.PyPDFDirectoryLoader`

## How do I turn the documents into chunks for the database?
- We're going to need a text splitter - fortunately `langchain` comes with a few
- Install them - `pip install langchain_text_splitters`
- We also need an embedding model, it is how we turn a chunk of text into a vector of numbers
- To do this locally, we're going to use Ollama again to grab our embedding model - `ollama pull nomic-embed-text`

## Putting it all together
- Look at the code in `populate_database.py`
- Look at the PDFs in `data/`
- Run `python populate_database.py`
- You should see some output saying documents are being added to the database
- Now run `python query_data.py "What are the card types in Ticket to Ride?"`


