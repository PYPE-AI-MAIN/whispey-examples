# Simple Voice Agent with Whispey

A basic LiveKit voice agent that integrates with Whispey for voice analytics.

## Quick Start

1. **Create and activate virtual environment:**
   ```bash
   python -m venv venv
   source venv/bin/activate  # On macOS/Linux
   # or
   venv\Scripts\activate     # On Windows
   ```

2. **Install dependencies:**
   ```bash
   pip install -r requirements.txt
   ```

2. **Set up environment variables:**
   ```bash
   cp env.example .env
   # Edit .env with your Whispey credentials
   ```

3. **Run the agent:**
   ```bash
   python basic_agent.py console
   ```

4. **When you exit the session**, it will log:
   - Usage metrics summary
   - session data  

## Requirements

- Python 3.9+
- Whispey API key and agent ID
- OpenAI API key (for LLM and TTS)
- Deepgram API key (for speech-to-text)
