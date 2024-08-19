### Overview

The HTML file defines a basic chatbot that listens to user input via a microphone, processes the input, and provides a relevant response based on predefined patterns. The chatbot operates using a graph structure to determine the flow of conversation.

### JavaScript Classes

1. **Falas Class**: 
   - Stores possible user inputs (triggers) and corresponding bot responses.
   - Uses a graph (`Grafo`) to manage conversation flow.
   - The `GetFala` method checks if user input matches any triggers and returns a response based on the current node in the graph.

2. **Grafo Class**:
   - Manages the conversation's state through nodes and edges in a graph.
   - Each node represents a conversation state, and edges define possible transitions.
   - `saltar` method moves to a new node if it's adjacent to the current one.
   - `GetNosAdj` method returns the adjacent nodes, including the current node.

3. **MatchInputResponse Class**:
   - Acts as a wrapper for the `Falas` class, handling the input and returning a response.

4. **Pesquisa Class**:
   - A React component that manages the chatbot interface.
   - Handles user input through speech recognition and updates the state with the recognized text and corresponding bot response.
   - `InputAudio` method activates the microphone, processes the input, and triggers a bot response.
   - Renders the chatbot interface, including the input and response messages.

### Key Features

- **Speech Recognition**: The chatbot listens for user input through a microphone using the Web Speech API's `SpeechRecognition`.
- **Speech Synthesis**: The bot's responses are spoken aloud using the Web Speech API's `SpeechSynthesis`.
- **Graph-Based Conversation Flow**: The bot's responses are determined based on the current node in a graph, allowing for more structured and dynamic interactions.

### How It Works

1. **User Interaction**: When the user clicks the microphone button, the bot listens to the user's input.
2. **Processing Input**: The input is matched against predefined patterns in the `Falas` class.
3. **Generating a Response**: If a match is found, a response is selected from the corresponding set of responses. The bot also updates the graph's current node to reflect the conversation's state.
4. **Output**: The response is displayed on the screen and spoken aloud.

This code is a basic example of how to implement a speech-enabled chatbot using React and JavaScript, with a simple graph-based logic to manage conversation flow.
