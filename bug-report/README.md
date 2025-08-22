# LiveKit Voice Agent - Hindi Agricultural Assistant

A LiveKit-based voice agent that assists farmers and Farmer Producer Organizations (FPOs) in Hindi, providing information about agricultural services and collecting business details.

## Features

- **Hindi Speech Recognition** using Sarvam STT
- **Natural Hindi Conversation** with ElevenLabs TTS
- **Agricultural Domain Expertise** for FPO assistance
- **Bug Reporting Integration** with Whispey observability
- **Structured Call Flow** with priority-based questioning

## Prerequisites

- Python 3.8 or higher
- OpenAI API key
- ElevenLabs API key
- Sarvam API credentials
- Whispey project setup

## Installation

### 1. Clone the Repository

```bash
git clone <your-repo-url>
cd <your-repo-name>
```

### 2. Create Virtual Environment

```bash
# Create virtual environment
python -m venv venv

# Activate virtual environment
# On Windows:
venv\Scripts\activate
# On macOS/Linux:
source venv/bin/activate
```

### 3. Install Dependencies

```bash
# Install requirements
pip install -r requirements.txt

# Force update whispey to latest version
pip install --upgrade --force-reinstall whispey
```

### 4. Environment Configuration

Create a `.env` file in the project root with the following variables:

```env
# OpenAI Configuration
OPENAI_API_KEY=sk-your_openai_api_key_here

# ElevenLabs Configuration
ELEVENLABS_API_KEY=your_elevenlabs_api_key_here

# Sarvam Configuration (for Hindi STT)
SARVAM_API_KEY=your_sarvam_api_key_here

# Whispey Configuration (for observability)
WHISPEY_API_KEY=pype_your_whispey_api_key_here
```

### 5. Whispey Setup

1. **Sign up**: Go to [https://www.whispey.xyz/](https://www.whispey.xyz/)
2. **Get Agent ID**: From the dashboard, get your Agent ID
3. **Generate API Key**: From account settings, generate your API key
4. **Update your code**: Replace the agent_id in `agent.py`:
   ```python
   pype = LivekitObserve(
       agent_id="your-agent-id-from-dashboard",  # Replace this
       apikey="your_whispey_api_key_here"       # Add to .env file
   )
   ```

## Running the Agent

### Console Testing (Development)

Test the agent locally in console mode:

```bash
python agent.py console
```

This will start the agent in console mode where you can type messages to test the conversation flow.

### Development Server

Run the agent in development mode:

```bash
python agent.py dev
```

### Production Deployment

For production deployment:

```bash
python agent.py start
```

## Testing the Agent

### Console Testing Commands

1. **Start Console Mode**:
   ```bash
   python agent.py console
   ```

2. **Test Hindi Conversation**:
   - Type: `हैलो` (Hello)
   - The agent should respond with the greeting message
   - Continue the conversation in Hindi

3. **Test Bug Reporting**:
   - Type: `इशू है` (There's an issue)
   - The agent should respond with bug reporting flow

### Testing Conversation Flow

The agent follows a structured conversation flow based on the business logic defined in the code. Test the conversation by interacting with the agent in console mode.

### View Analytics

After running the agent, you can view detailed analytics at [https://www.whispey.xyz/](https://www.whispey.xyz/) including:
- Real-time call monitoring
- Cost tracking for STT, TTS, and LLM usage
- Performance metrics and latency analysis
- Call transcripts and quality scores

## Troubleshooting

### Common Issues

1. **Import Error: whispey**
   ```bash
   pip install --upgrade --force-reinstall whispey
   ```

2. **Audio Issues**
   - Ensure microphone permissions are granted
   - Check VAD settings in the code

3. **API Key Issues**
   - Verify all API keys in `.env` file
   - Check API key validity and quotas

4. **Hindi Speech Recognition Issues**
   - Ensure Sarvam API is working
   - Check language settings (`hi-IN`)

## Dependencies

- `livekit-agents`: Core LiveKit agents framework
- `livekit-plugins-openai`: OpenAI LLM integration
- `livekit-plugins-elevenlabs`: ElevenLabs TTS
- `livekit-plugins-silero`: Silero VAD
- `livekit-plugins-sarvam`: Sarvam Hindi STT
- `python-dotenv`: Environment variable management
- `whispey`: Observability and bug reporting

## API References

- [LiveKit Agents Documentation](https://docs.livekit.io/agents/)
- [OpenAI API](https://platform.openai.com/docs/)
- [ElevenLabs API](https://elevenlabs.io/docs/)
- [Sarvam API](https://sarvam.ai/)
- [Whispey Documentation](https://github.com/PYPE-AI-MAIN/whispey)

## Support

For issues and questions:

1. Check the troubleshooting section above
2. Review LiveKit agents documentation
3. Verify all API keys and configurations
4. Test in console mode first before production deployment

## License

[Add your license information here]