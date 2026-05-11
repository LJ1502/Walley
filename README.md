# Walley - Real-Time Budget APP made to integrate with GX Bank

Mobile application for real-time budgeting. The app captures unread inbox from emails or sms via a real-time scrape, send it to our JAM AI base backend to check for any personal transaction biling to be aded to daily budgeting. There is an AI layer , behind the APP to capture any potential fraud activity as well
---
## Team
1. LOO JIUN WEI
2. LEE JARRELL
3. ANGEL TAN KE QIN
4. JANISA GOH SHI JIE
5. IVAN FONG JUN TOH

Google Drive Link : https://drive.google.com/drive/folders/1if4qai58oJMVypd6sEohh-i3yNvWhZZp
---


## System Architecture

* **Frontend:** React Native (Expo)
* **Backend:** Python (FastAPI, WebSockets)
* **Transcription:** AssemblyAI (Speaker Diarization & Language Detection)
* **Analysis Engine:** JamAI Base (LLM Action Tables)

## Prerequisites

* Node.js (LTS)
* Python 3.10 or higher
* FFmpeg (Required for audio processing)
* Expo Go (Android) or Android Studio Emulator

## Installation & Setup

### Backend

1.  Navigate to the backend directory.
2.  Create and activate a virtual environment:
    ```bash
    python -m venv venv
    # Windows:
    .\venv\Scripts\activate
    # Mac/Linux:
    source venv/bin/activate
    ```
3.  Install dependencies:
    ```bash
    pip install fastapi uvicorn websockets python-dotenv assemblyai jamaibase
    ```
4.  Create a `.env` file in the root directory:
    ```ini
    JAMAI_PROJECT_ID=your_project_id
    JAMAI_API_KEY=your_api_key
    ASSEMBLYAI_API_KEY=your_assembly_key
    ```
5.  Start the server:
    ```bash
    python main.py
    ```

### Mobile App

1.  Navigate to the app directory.
2.  Install dependencies:
    ```bash
    npm install
    ```
3.  Update the WebSocket configuration in `App.jsx`:
    ```javascript
    const SERVER_URL = 'ws://<YOUR_LAPTOP_IP>:8000/ws/audio';
    ```
4.  Start the application:
    ```bash
    npx expo start
    ```

## Usage

* **Call Monitoring:** Ensure the call is on **Speakerphone**. The app records audio in 10-second chunks via the microphone.
* **SMS Scanner:** Copy suspicious text messages into the scanner input for analysis.
* **Background Operation:** The app utilizes a foreground service location task to maintain active state during calls.

## License

MIT
