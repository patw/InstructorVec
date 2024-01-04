# InstructorVec

A small vector API service for generating quantized instructor-large vectors.  This is used in various other projects under my github repos

## Local Installation

```
pip install -r requirements.txt
```

## Local Running

```
uvicorn main:app --host 0.0.0.0 --port 3005
```

**Warning**: The first run will be VERY slow to load

Visit `http://localhost:3005/docs` in a browser once it's loaded

Call it in python like this:

```
# Function to call the text embedder
def embed(text):
    response = requests.get(embedder["embedding_endpoint"], params={"text":text, "instruction": "Represent this text for retrieval:" }, headers={"accept": "application/json"})
    vector_embedding = response.json()
    return vector_embedding
```
