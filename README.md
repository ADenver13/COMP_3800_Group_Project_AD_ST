# Quizlet Flashcard Generator Chatbot
### Created By: Sofia Toropova, Aiden Dever

This chatbot helps users by generating a set of flashcards from text supplied by the user that can be imported into Quizlet.

## Table of Contents

- [Features](#features)
- [Langchain](#langchain)
- [Setup](#setup)
- [Usage](#usage)
- [License](#license)

## Features

- **Flashcard Generation**: Users can upload a file, and the bot will create flashcards.
- **Tone Setting**: The bot can set the flashcards to a certain tone (formal, brief, explainer, etc.).
- **Recommendations**: The bot can recognize that there is more to a certain topic than provided in the text, and provide additional information. This feature can be turned off.

## Langchain

  Langchain is a framework for integrating multiple LLMs into applications in an easy to understand way. In this case, we create an agent by providing the agent tools and using OpenAI's API to decide which tool to use based on user
  input and tool descriptions provided. More information can be found [here](https://python.langchain.com/v0.1/docs/modules/agents/).

## Setup

1. **Clone the repository**:
   ```bash
   git clone https://github.com/ADenver13/COMP_3800_Group_Project_AD_ST.git
   cd COMP_3800_Group_Project_AD_ST
   ```
2. **Install Requirements**:
   ```bash
   pip install -r requirements.txt
   ```
3. **.env**
  In order to use the OPENAI API and Langchain, API keys are required. These will have to be set in a .env file in the format below:
  ```bash
  LANGCHAIN_API_KEY = 'KEY_HERE'
  OPENAI_API_KEY = 'KEY_HERE'
  ```
After this, you can run all code inside the Jupyter Notebook.

## Usage
  The chatbot can be run just like any other Jupyter Notebook.

## Tips
  - The bot does have a tendency to hallucinate, as do all LLMs. This can impact your flashcards, particularly the additional reccomendations not found in the text. This feature can be turned off.
  - Currently, the bot wil tell you what it's thinking and try to rationalize decisions to you. This can be removed by setting verbose=False in the following code:
   ```python
   agent_executor = initialize_agent(
    tools=tools,
    llm=OpenAI(temperature=0.4), #Could use some adjusting
    agent_type=AgentType.ZERO_SHOT_REACT_DESCRIPTION,
    verbose=True
   )
   ```

   
