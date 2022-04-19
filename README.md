# Rasa-chatbot

This repository contains all code for a website and associated chatbot I built. The chatbot is made using [Rasa](https://rasa.com/), an open-source machine learning framework for conversational AI. To use the Rasa chatbot on the website, a widget is used from [this Github repository](https://github.com/botfront/rasa-webchat). 


## Types of Chatbots

1) Menu/Button based chatbots - These chatbots answer a fix set of repeating questions (FAQs). Questions are displayed in the form of buttons or menu. It is similar to the automated customer care phone call menus.

2) Contextual chatbots - These chatbots make use of Machine Learning to remember the context of the conversation with specific users. These chatbots can learn and improve through conversations.

## How does Rasa work ?

 1. Understand the question of the user, what answer he is expecting .
 2. Maintain the conversation flow, i.e reply to him based on the question/query and converse further.

#### Natural Language Understanding - NLU is responsible for understanding user's message. Identifying intent/purpose of the user message.

1) **Intent** - can be defined as a label or class. Different messages from users belong to a same intent. For example - "Hello", "Good morning", "Hi", belong to the "Greet" intent. The purpose of the user's message is to greet. All intents are registered in a file called nlu.md, inside the data folder.

2) **Response** - bot's reply to the user. These responses are stored in a file called domain.yml. This file also maintains a list of all intents.

3) **Story** - can be defined as the conversation flow between the user and the bot. Stories are stored in a file called stories.md, inside the data folder.

4) **Config.yml** - file consist of the complete pipeline of classes used for tokenization to intent classification.

5) **Actions** - Actions can used to return dynamic output, for example current time, date, live match score, top headlines etc. Actions can be defined in the actions.py file.

6) **Entity** - Entity can be defined as name of a person, place, date, time etc. Chatbots should be able to extract entities from the user messages. Let's see how it is done. Inside nlu.md file, entity values must be  mentioned in square brackets [], and entity name must be mentioned in braces () alongside the entity value.

7) **domain** - The domain defines the universe in which your assistant operates. It specifies the intents, entities, slots, responses, forms, and actions your bot should know about. It also defines a configuration for conversation sessions. 

### To run the Rasa models, do the following in a command prompt window(Annaconda):
  - `conda create -n rasa_ai python=3.7.6`
  - `conda activate rasa_ai`

  - `pip install --upgrade pip==20.2`
  - `pip install --use-deprecated=legacy-resolver rasa-x --extra-index-url https://pypi.rasa.com/simple`

  - `pip install tensorflow`
  - `pip install ujson`
  - `pip install rasa`
  
### To run

create a folder chatbot (in drive) and change the directory using cd (with folder path link copy from  drive) path to new folder (i.e chatbot) you have created once you are in, type `rasa init`
it will ask you for which directory type `.` (dot) and hit enter `y` it will give a inbuild bot with already build respones.


TO DO: To make a changes in file use text editor like sublime text editor or visual studio 
- once changes are done in files (nlu.yml.domai.yml etc.) retrain model `rasa train`
- `rasa shell` now you can communicate with bot.

To run do the following in another command prompt window:

- `rasa run actions` for checking the actions it will help to detect the errors.



