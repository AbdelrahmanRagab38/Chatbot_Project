# Chatbot_Project
The dataset for a chatbot is a JSON file that has disparate tags like goodbye, greetings, pharmacy_search, hospital_search, etc. Every tag has a list of patterns that a user can ask, and the chatbot will respond according to that pattern.
# Project File Structure

Train_chatbot.py — In this file, we will build and train the deep learning model that can classify and identify what the user is asking to the bot.

Gui_Chatbot.py — This file is where we will build a graphical user interface to chat with our trained chatbot.

Intents.json — The intents file has all the data that we will use to train the model. It contains a collection of tags with their corresponding patterns and responses.

Chatbot_model.h5 — This is a hierarchical data format file in which we have stored the weights and the architecture of our trained model.

Classes.pkl — The pickle file can be used to store all the tag names to classify when we are predicting the message.

Words.pkl — The words.pkl pickle file contains all the unique words that are the vocabulary of our model.


We can summerize the building of this chatbot in 5 steps:

Step 1. Import Libraries and Load the Data
Step 2. Preprocessing the Data (lowercase , tokenization and lemetization ) 
Step 3. Create Training and Testing Data
Step 4. Training the Model
The architecture of our model will be a neural network consisting of 3 dense layers. The first layer has 128 neurons, the second one has 64 and the last layer will have the same neurons as the number of classes. The dropout layers are introduced to reduce overfitting of the model. We have used the SGD optimizer and fit the data to start the training of the model. After the training of 200 epochs is completed, we then save the trained model using the Keras model.save(“chatbot_model.h5”) function.
Step 5. Interacting With the Chatbot
Our model is ready to chat, so now let’s create a nice graphical user interface for our chatbot in a new file.  name of the file is gui_chatbot.py
In our GUI file, we will be using the Tkinter module to build the structure of the desktop application and then we will capture the user message and again perform some preprocessing before we input the message into our trained model.
The model will then predict the tag of the user’s message, and we will randomly select the response from the list of responses in our intents file.


