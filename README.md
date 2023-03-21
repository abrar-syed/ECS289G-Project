# [ECS289G-Project] Constructing Compelling Narratives: A MultiModal Framework for Story Generation

## How to run?

After cloning the repository

### Client

Install and check that the client compiles:
```
cd client
npm i
npm run build
```

### Backend

Install and activate the environment (conda provided):
```
conda env create -f environment.yml
conda activate MultiModalStory
```

Install environment globally in the directory: 
```
pip install -e .
pip install git+https://github.com/openai/CLIP.git
```

After installation run:
```
python -m spacy download en_core_web_sm
```
In python terminal:
```
nltk.download('wordnet')
nltk.download('sentiwordnet')
nltk.download('averaged_perceptron_tagger')
```

### Large Data Management

```
dvc pull -f
```

Which will pull:
- backend/outputs (five preset stories)
- backend/story_generator/downloaded (transformers)
- client/public/unsplash25k (styled images)

### Running the framework during developemnt

Client: 
```
cd client
npm run devw
```

Backend (with server auto reload): 
```
uvicorn backend.server:app --reload --reload-dir backend
```

Open the uvicorn server `localhost:8000` in your web browser
