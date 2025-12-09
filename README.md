# ChatGPT Clone

A Streamlit-based ChatGPT clone built with OpenAI Agents Python library, featuring web search, file search, image generation, code interpretation, and MCP (Model Context Protocol) tool integration.

## Features

- 🤖 **AI Assistant**: Powered by OpenAI Agents with conversational memory
- 🔍 **Web Search**: Search the web for current information and answers
- 📁 **File Search**: Search and analyze uploaded files using vector stores
- 🎨 **Image Generation**: Generate images using DALL-E
- 💻 **Code Interpreter**: Write and execute Python code to answer questions
- ⚒️ **MCP Tools**: Integration with Model Context Protocol servers
  - Yahoo Finance (yfinance) for financial data
  - Timezone server for time-related queries
  - Context7 for software documentation
- 💾 **Session Management**: Persistent chat history using SQLite
- 📸 **Image Upload**: Support for image inputs (JPG, JPEG, PNG)
- 📄 **File Upload**: Support for text file uploads

## Requirements

- Python >= 3.13
- OpenAI API key
- Vector Store ID (for file search functionality)

## Installation

1. Clone the repository:
```bash
git clone <repository-url>
cd chatgpt-clone
```

2. Install dependencies using `uv`:
```bash
uv sync
```

Or using pip:
```bash
pip install -r requirements.txt
```

3. Create a `.env` file in the root directory:
```env
OPENAI_API_KEY=your_openai_api_key_here
VECTOR_STORE_ID=your_vector_store_id_here
```

## Usage

1. Start the Streamlit application:
```bash
streamlit run main.py
```

2. Open your browser and navigate to the URL shown in the terminal (typically `http://localhost:8501`)

3. Start chatting with the assistant! You can:
   - Type messages in the chat input
   - Upload text files (`.txt`) for analysis
   - Upload images (`.jpg`, `.jpeg`, `.png`) for image-based queries
   - Use the sidebar to reset conversation memory

## Tools and Capabilities

### Web Search Tool
Automatically searches the web when:
- Questions about current or future events
- Information not in training data
- When the assistant is uncertain about an answer

### File Search Tool
Searches uploaded files when:
- Questions about personal facts or information
- Queries about specific files
- Uses vector store for semantic search

### Code Interpreter Tool
Executes Python code when:
- Mathematical calculations are needed
- Data analysis is required
- Code execution can help answer the question

### Image Generation Tool
Generates images using DALL-E with:
- High quality output
- JPEG format
- Partial image streaming

### MCP Tools
- **Yahoo Finance**: Get stock prices, financial data, and market information
- **Timezone Server**: Get time and timezone information (default: America/New_York)
- **Context7**: Access software project documentation

## Project Structure

```
chatgpt-clone/
├── main.py                 # Main Streamlit application
├── pyproject.toml          # Project dependencies and configuration
├── README.md               # This file
├── .env                    # Environment variables (not in git)
├── chat-gpt-clone-memory.db # SQLite database for chat history
└── .gitignore              # Git ignore rules
```

## Configuration

### Environment Variables

- `OPENAI_API_KEY`: Your OpenAI API key (required)
- `VECTOR_STORE_ID`: Your OpenAI Vector Store ID for file search (required)

### MCP Servers

The application uses two MCP servers:
- `mcp-yahoo-finance`: For financial data queries
- `mcp-server-time`: For timezone and time queries

These are automatically started using `uvx` when the application runs.

## Session Management

Chat history is persisted in a SQLite database (`chat-gpt-clone-memory.db`). You can reset the conversation memory using the "Reset memory" button in the sidebar.

## Dependencies

- `openai-agents[viz]>=0.2.6`: OpenAI Agents Python library
- `streamlit>=1.48.0`: Web application framework
- `python-dotenv>=1.1.1`: Environment variable management
- `graphviz>=0.21`: Visualization support

## Development

For development, install the dev dependencies:
```bash
uv sync --dev
```

This includes:
- `ipykernel>=6.30.1`: For Jupyter notebook support

## Reference

This project is based on the [OpenAI Agents Python](https://openai.github.io/openai-agents-python/) library.

## License

[Add your license here]
