# Digital Twin - Vedant Pandit

An AI-powered digital twin chatbot that represents Vedant Pandit on his website. The chatbot can answer questions about Vedant's career, background, skills, and experience using information from his LinkedIn profile and summary.

## Features

- 🤖 Powered by OpenAI's GPT-4o-mini
- 📄 Extracts information from LinkedIn PDF profile
- 📧 Records user contact information
- 🔔 Sends notifications via Pushover when users show interest
- 💬 Interactive web interface built with Gradio
- 🎯 Records unknown questions for continuous improvement

## 🎥 Demo

[📹 Watch Demo Video](https://www.youtube.com/watch?v=EFeaOhdHJ04)

## Prerequisites

- Python 3.11 or higher
- [uv](https://github.com/astral-sh/uv) package manager
- OpenAI API key
- Pushover account (for notifications)

## Quick Start

### 1. Clone or Set Up the Project

If cloning from GitHub:
```bash
git clone https://github.com/yourusername/digital-twin-vedant.git
cd digital-twin-vedant
```

### 2. Configure Environment Variables

Create a `.env` file with your credentials:
```bash
OPENAI_API_KEY=your_openai_api_key_here
PUSHOVER_TOKEN=your_pushover_token_here
PUSHOVER_USER=your_pushover_user_key_here
```

### 3. Run the Application

That's it! Just run:
```bash
uv run app.py
```

The `uv run` command will:
- Automatically create a virtual environment (`.venv/`)
- Install all dependencies from `pyproject.toml`
- Launch your application

The Gradio interface will launch at `http://127.0.0.1:7860`

## Dependencies

The following packages are automatically installed when you run `uv run app.py`:

- **openai** (>=1.0.0) - OpenAI API client
- **python-dotenv** (>=1.0.0) - Environment variable management
- **requests** (>=2.31.0) - HTTP requests for Pushover notifications
- **pypdf** (>=3.17.0) - PDF text extraction from LinkedIn profile
- **gradio** (>=4.0.0) - Web UI framework

Plus all their dependencies (63 packages total).

## Project Structure

```
digital-twin-vedant/
├── .env                            # Your secrets (NOT in git)
├── .gitignore                      # Files to ignore in git
├── .venv/                          # Virtual environment (auto-created, NOT in git)
├── README.md                       # This file
├── app.py                          # Main application
├── info/
│   ├── summary.txt                 # Your personal summary
│   └── Vedant_Pandit_Linkedin.pdf  # Your LinkedIn PDF
├── pyproject.toml                  # Project dependencies and metadata
└── uv.lock                         # Locked dependency versions (auto-generated)
```

## How It Works

1. **Information Loading**: The application reads Vedant's summary and LinkedIn profile on startup
2. **Chat Interface**: Users interact with the AI through a Gradio web interface
3. **Tool Calling**: The AI can use two tools:
   - `record_user_details`: Records interested users' email addresses
   - `record_unknown_question`: Logs questions that couldn't be answered
4. **Notifications**: When users provide contact information or ask unknown questions, notifications are sent via Pushover

## Customization

To adapt this digital twin for yourself:

1. Replace `info/Vedant_Pandit_Linkedin.pdf` with your LinkedIn profile PDF
2. Update `info/summary.txt` with your personal summary
3. Modify the `self.name` in the `Me` class in `app.py` to your name
4. Update this README with your information

## Troubleshooting

### "Module not found" error
Run `uv sync` to ensure all dependencies are installed.

### Port already in use
Gradio will automatically try the next available port if 7860 is busy.

### OpenAI API error
Check that your `OPENAI_API_KEY` in `.env` is correct and has credit.

### TypeError with ChatInterface
If you see `TypeError: ChatInterface.__init__() got an unexpected keyword argument`, make sure you're using the correct Gradio API format without `type="messages"`.

## Tips

- **Testing locally:** Always test with `uv run app.py`
- **API costs:** Monitor your OpenAI usage at https://platform.openai.com/usage
- **Notifications:** Test Pushover notifications by visiting the Gradio interface and providing an email
- **Updates:** Keep dependencies updated with `uv sync --upgrade`

## License

MIT License - feel free to use this for your own digital twin!

---

Built with ❤️ using OpenAI, Gradio, and Python. Created while enrolled in **[AI Engineer Agentic Track: The Complete Agent & MCP Course](https://www.udemy.com/course/the-complete-agentic-ai-engineering-course/)** on Udemy.

