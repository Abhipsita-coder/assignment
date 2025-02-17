# AI Voice Assistant with WebSockets and ElevenLabs API

This project creates an AI-powered voice assistant using WebSockets for real-time audio streaming. It integrates with Twilio to handle incoming calls and ElevenLabs for text-to-speech synthesis. Additionally, it can process text input through WebSockets and generate responses using the Gemini language model.

## Features

- **Twilio Integration**: Handles incoming calls and streams audio using WebSockets.
- **ElevenLabs Text-to-Speech**: Converts text responses into audio using ElevenLabs API.
- **Gemini AI**: Generates text responses to user queries, which are converted to speech.
- **DTMF Input Handling**: Supports keypad input (DTMF) from the caller.
- **Real-Time Communication**: Real-time audio input and output via WebSockets.
- **WebSocket Server**: Enables two-way communication between the server and clients.

## Prerequisites

Before running the project, make sure you have the following:

- Node.js and npm installed.
- A Twilio account with API keys.
- An ElevenLabs API key.
- A Gemini API key (or replace it with your preferred AI model).
- A `.env` file for storing environment variables securely.

## Installation

1. Clone the repository:

   ```bash
   git clone https://github.com/yourusername/ai-voice-assistant.git
   cd ai-voice-assistant
2. Install the required dependencies:


  npm install
3 Create a .env file in the root directory with the following variables:
TWILIO_ACCOUNT_SID=your_twilio_account_sid
TWILIO_AUTH_TOKEN=your_twilio_auth_token
TWILIO_PHONE_NUMBER=your_twilio_phone_number
ELEVENLABS_VOICE_ID=your_elevenlabs_voice_id
XI_API_KEY=your_elevenlabs_api_key
GEMINI_API_KEY=your_gemini_api_key
DOMAIN=your_server_domain
PORT=3000
Usage
Start the server:

npm start 
The server will run on the specified port (default 3000). The Twilio webhook is set up to handle incoming calls and stream audio via WebSockets to the server.

When a call is made to the Twilio phone number, the server will respond with an interactive voice message and wait for input via DTMF or text.

The AI assistant will process the user's input and respond with a generated text and audio output.

API Endpoints
POST /voice: This is the Twilio webhook that handles incoming calls and streams audio via WebSockets.

Example:


<Response>
  <Connect>
    <Stream url="wss://yourdomain.com/media-stream"/>
  </Connect>
</Response>
WebSocket Events
event: "media": This event sends audio data (base64-encoded).
event: "text": This event sends a text response to the client.
Example Flow
A user calls the Twilio number.
The server sends a greeting message: "Hello, this is your AI assistant. Type or say something!"
The user interacts by typing or using DTMF keys.
The server processes the input, generates a response using Gemini, and converts it to speech using ElevenLabs.
The response is sent back to the user as both text and audio.
Contribution
Feel free to fork this project, open issues, or submit pull requests!

License
This project is licensed under the MIT License.
