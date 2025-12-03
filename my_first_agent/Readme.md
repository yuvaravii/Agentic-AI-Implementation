# Description 
- Creating my first agent using google ADK (agent development kit)

---
# Requirements 
'google-adk',
'python-dotenv'

---
# References
[Google starter for Agent documentation](https://google.github.io/adk-docs/get-started/python/)

---
# Execution logs and instructions
- The API key might not work, as they are deleted after creation of first agent.

---
## Intializing Google projects
- ([Site to sign in and create google project](https://console.cloud.google.com/welcome/new?pli=1&authuser=3))

### Creation of project in google cloud platform
- On the left top corner, click the button "select a project"
- type a desirable name, the name does not allow "_".
- my desirable name "test ai agent"

### Creation of API key using google studio
- ([Link to Create API key](https://aistudio.google.com/app/u/3/api-keys))
- Create new API key
- To make the AI key is relevant with the project we created in google cloud projects. Choose "Chosse an imported project"--> "import project"--> "select the google cloud platform project 'test ai agent'" --> write a name to identify the api key --> my desirable name: "test ai agent key"
- copy the API key after creation.
- ([Link to view the limit of free tier Google models](https://ai.google.dev/gemini-api/docs/rate-limits))

### Creating first agent
- we have all the inputs needed now.
- Don't use other package manager like UV, conda.. (did not work for me)
- Try using only python environment

__*1. Creating the python virtual environment using the terminal*__ 
```bash
python -m venv .venv
source .venv/bin/activate
pip freeze > requirements.txt
pip install -r requirments.txt
```

__*2. adding necessary libraries*__ 
```bash
pip install google-adk
```


__*3. Create new agentic project using terminal, after moving into the required folder*__ 
```bash
adk create my_agent
```
- The above step allows you to create all the necessary file for initializing a project. This would require following details to complete the initialization
    1. Choose model for the root agent:
        1. gemini-2.5-flash
        2. Other models (fill later)
    2. Choose a backend:
        1. Google AI
        2. Vertex AI
    3. Enter Google API Key:
        1. "Enter your API key"

- To run the agent on web for easier readability and understandability use , press "ctrl+c" to quit
```bash
adk web --port 8000
``` 
- The following are initialized automatically:
    1. __init__.py  # for managing the file as package allowing to import different modules and functions
    2. .env         # file for managing the api key
    3. agent.py     # this is the actual agent(Just like a person) --> has model(brain),name(person name), description(capability of a person), instruction(task to perform), tools(just like all person, like hammer for carpenter). This is the root agent on which whole agentic ai starts with or an entry point

    *We can create tools(functions, search engine, other tools too) for the LLM to access*


