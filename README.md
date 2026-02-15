# Atlas 🍎

**Local AI Agent for File Management**

Atlas is your personal AI assistant that runs on your computer. It manages your files, automates tasks, and remembers what you tell it across all your sessions. Features a beautiful terminal UI built with Rich.

---

## What Atlas Does

**Comprehensive File Management**
- Create, read, write, delete, and move files through conversation
- Copy and move multiple files at once with batch operations
- Read specific lines from large files with `readFileLines`
- Get directory trees with customizable depth
- Rename and check file existence and sizes
- List directory contents instantly

**Smart Memory System**
- Key-value memory storage for user preferences and important facts
- `rememberFact`, `recallFact`, `forgetFact`, `listMemories` tools
- Persistent across sessions - stored locally in JSON format
- Perfect for remembering project names, preferences, and context

**Beautiful Terminal UI**
- Rich console interface with ASCII art branding
- Tool execution panels showing parameters and results  
- Real-time status indicators ("Thinking...", "Loading...")
- Markdown rendering for agent responses
- Color-coded output for better readability

**Built for Privacy**
- Everything runs on your local machine
- Your files never leave your computer
- All data stored locally, not in the cloud
- You own all your data and conversations

---

## Quick Start

**1. Requirements**
- Python 3.8+
- GROQ API key (get one at [groq.com](https://groq.com))

**2. Installation**
```bash
git clone https://github.com/tawfickobtan/Atlas
cd Atlas
pip install -r requirements.txt
```

**3. Configuration**
Set your API key:
```bash
# Windows PowerShell
$env:GROQ_API_KEY="your-groq-api-key"

# Mac/Linux
export GROQ_API_KEY="your-groq-api-key"

# CMD
setx GROQ_API_KEY "your-groq-api-key"
```

Edit `configuration/config.json` to change the model or settings.

**4. Run Atlas**
```bash
python atlas.py
```

---

## Why Atlas?

✅ **Persistent Memory** - Remembers facts across sessions  
✅ **Local & Private** - All data stays on your machine  
✅ **Action-Oriented** - Does the work, not just advises  
✅ **Beautiful UI** - Rich terminal interface with panels and colors  
✅ **Batch Operations** - Move/copy multiple files at once  
✅ **Safe by Design** - Protected files prevent accidental modifications

---

## Available Tools

### File Operations
- `createFile`, `writeIntoFile`, `readFile`, `readFileLines`
- `delete`, `moveFile`, `copyFile`, `renameFile`  
- `moveMultipleFiles`, `copyMultipleFiles` (batch operations)
- `fileExists`, `getFileSize`

### Directory Operations  
- `createDirectory`, `deleteDirectory`
- `getItemsInPath`, `getCurrentDirectory`
- `getDirectoryTree` (visualize folder structure with depth control)

### Memory Management
- `rememberFact` - Store key-value pairs persistently
- `recallFact` - Retrieve stored information
- `forgetFact` - Delete specific memories
- `listMemories` - View all stored facts

---

## Project Structure

```
Atlas/
├── atlas.py             # Main entry point with Rich UI
├── requirements.txt      # Python dependencies
├── README.md            # Documentation
├── agent/
│   ├── agent.py         # Core Agent class with tool calling
│   ├── tools.py         # Tool implementations
│   └── tools.json       # Tool definitions for function calling
├── configuration/
│   ├── config.json      # Model and API configuration
│   └── AGENT.md         # System prompt and personality
└── memory/
    └── memory.json      # Persistent key-value storage
```

---

## Technical Details

**Architecture:**
- Built on OpenAI-compatible API format (via GROQ)
- Function calling with automatic tool execution
- Rich console library for beautiful terminal UI
- JSON-based configuration and memory storage

**Model:** Default is `openai/gpt-oss-120b` (configurable in config.json)

**Dependencies:**
- `openai>=1.0.0` - API client
- `rich>=13.0.0` - Terminal UI
- `requests>=2.31.0` - HTTP requests  
- `sentence-transformers` - Text processing
- `numpy` - Numerical operations

**Protected Files:**  
Atlas won't modify these critical files: `agent.py`, `tools.py`, `tools.json`, `config.json`, `AGENT.md`, `requirements.txt`, `.gitignore`

---

## Configuration

Edit `configuration/config.json`:
```json
{
  "base_url": "https://api.groq.com/openai/v1",
  "model": "openai/gpt-oss-120b",
  "version": "1.0.1"
}
```

Customize the agent personality in `configuration/AGENT.md` to change how Atlas responds and behaves.

---

## Contributing

Contributions are welcome! Feel free to:
- Report bugs and issues
- Suggest new tools or features
- Improve documentation
- Submit pull requests

💼 [Check out my LinkedIn](https://www.linkedin.com/in/tawfic-kobtan) for more projects and updates!

