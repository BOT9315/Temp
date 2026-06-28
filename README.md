# Advanced LLM Workspace

A professional-grade, feature-rich LLM application built with React and the Anthropic Claude API. Use it as a standalone tool, learning resource, or starting point for your AI projects.

## 🌟 Features

### Core Functionality
- **Three Operating Modes**: Chat, Completion, and Analysis
- **Multiple Models**: Opus, Sonnet, and Haiku support
- **Advanced Parameters**: Temperature, Top-P, Max Tokens control
- **System Prompts**: Customize AI behavior and expertise
- **Response Formatting**: Text, Markdown, JSON, and Summary formats

### Advanced Capabilities
- **Token Tracking**: Real-time token counting and cost estimation
- **Conversation Management**: Export chats as Markdown files
- **One-Click Presets**: Creative, Technical, Analytical, and Balanced presets
- **API Key Security**: Local storage, never transmitted externally
- **Multi-turn Context**: Full conversation history for accurate responses

### Professional Tools
- Real-time streaming responses
- Message timestamps
- Token usage per message
- Estimated API costs
- Error handling and recovery
- Success confirmations

## 📋 System Requirements

- Modern web browser (Chrome, Firefox, Safari, Edge)
- Anthropic API key (get from [console.anthropic.com](https://console.anthropic.com))
- No installation needed - runs entirely in your browser

## 🚀 Quick Start

### 1. Open the Application
Download `index.html` and open it in your web browser:
```bash
# Option 1: Double-click the file
# Option 2: Drag to browser window
# Option 3: Right-click → Open with browser
```

### 2. Add Your API Key
- Click "Setup" when prompted
- Enter your Anthropic API key (from console.anthropic.com)
- Click "Save & Continue"
- Your key is stored locally in browser (never sent anywhere except to Anthropic's API)

### 3. Choose Your Mode
- **Chat**: Multi-turn conversation with memory
- **Completion**: Text generation from prompts
- **Analysis**: Content and document analysis

### 4. Adjust Parameters
- Temperature: Control creativity (0=deterministic, 2=very creative)
- Top-P: Control diversity (0.7-0.95 recommended)
- Max Tokens: Control response length (100-4000)
- System Prompt: Define the AI's behavior and expertise

### 5. Start Using
- Type your message/prompt
- Press Enter or click Send
- Wait for response
- Continue conversation or export chat

## 📖 Detailed Usage Guide

### Mode: Chat
**Best for**: Conversational interactions, Q&A, brainstorming

```
1. Select "Chat" mode
2. Start typing naturally
3. Each message is part of ongoing conversation
4. AI remembers context from previous messages
5. Ideal temperature: 0.7
```

### Mode: Completion
**Best for**: Text generation, creative writing, code

```
1. Select "Completion" mode
2. Enter starting text or prompt
3. AI generates continuation
4. Preset: Use "Creative" for writing or "Technical" for code
5. Ideal temperature: 0.8-1.2 for creative, 0.3-0.5 for technical
```

### Mode: Analysis
**Best for**: Summarization, extraction, research

```
1. Select "Analysis" mode
2. Paste document or content
3. Ask specific questions about content
4. Response format: Use "Summary" or "Markdown"
5. Ideal temperature: 0.3-0.5 for accuracy
```

## ⚙️ Parameter Guide

### Temperature
| Value | Behavior | Use Case |
|-------|----------|----------|
| 0.0 - 0.3 | Highly deterministic | Factual, code, translation |
| 0.4 - 0.7 | Balanced | General purpose, default |
| 0.8 - 1.2 | Creative | Writing, brainstorming |
| 1.3 - 2.0 | Very random | Ideation, experimental |

### Top-P (Nucleus Sampling)
| Value | Behavior | Note |
|-------|----------|------|
| 0.5 - 0.7 | Focused | Very narrow word choices |
| 0.8 - 0.9 | Balanced | Default recommended |
| 0.95 - 1.0 | Diverse | Broadest word selection |

### Max Tokens
| Value | Typical Output | Best For |
|-------|---|---|
| 100-300 | Short answers | Quick responses |
| 300-800 | Medium responses | General Q&A |
| 800-1500 | Long-form content | Articles, code |
| 1500-4000 | Very long content | Deep analysis, scripts |

## 🎯 Quick Presets

### Creative Preset
- Temperature: 1.2
- Top-P: 0.95
- System: "You are a creative writing assistant"
- Best for: Writing, storytelling, brainstorming

### Technical Preset
- Temperature: 0.3
- Top-P: 0.8
- System: "You are an expert programmer"
- Best for: Code, debugging, technical Q&A

### Analytical Preset
- Temperature: 0.5
- Top-P: 0.85
- System: "You are a data analyst"
- Best for: Analysis, research, data extraction

### Balanced Preset
- Temperature: 0.7
- Top-P: 0.9
- System: "You are a helpful AI assistant"
- Best for: General purpose, default use

## 💾 Exporting Conversations

### Export Process
1. Click "Export Chat" button
2. File automatically downloads as `.md` (Markdown)
3. Contains full conversation with timestamps and token counts

### File Contents
```markdown
# LLM Conversation Export

**Model:** claude-sonnet-4-6
**Date:** [timestamp]

---

**USER** (timestamp)
Your message here

---

**ASSISTANT** (timestamp)
Response here [X tokens]
```

## 📊 Token Usage & Costs

### Token Estimation
- Roughly 1 token ≈ 4 characters
- System prompt uses ~50-100 tokens
- Estimated in real-time

### Pricing (Claude Sonnet 4.6)
- Input: $3 per 1M tokens
- Output: $15 per 1M tokens
- Estimated cost shown in sidebar

### Example Costs
| Use Case | Avg Tokens | Est. Cost |
|----------|-----------|-----------|
| 5-message chat | 2,000 | $0.04 |
| Article summary | 1,500 | $0.03 |
| Code generation | 1,000 | $0.02 |
| 20-turn conversation | 5,000 | $0.10 |

## 🔒 Security & Privacy

### Local Storage
- API key stored in browser's localStorage
- Never transmitted except to Anthropic API
- Clear via "Change API Key" button
- Delete localStorage to fully clear

### Data Handling
- Messages are sent only to Anthropic
- Anthropic processes according to their privacy policy
- No data stored in this application
- Export conversations manually if you want to keep them

## 🛠️ Advanced Techniques

### Prompt Engineering
```
Technique 1: Chain of Thought
Prompt: "Think step by step: [your question]"
Effect: Better reasoning, more detailed answers

Technique 2: Role Playing
Prompt: "You are a [role]. [your question]"
Effect: Specialized expertise, specific tone

Technique 3: Few-Shot Learning
Update system prompt with examples:
"Examples of good responses:
- Input: X → Output: Y
- Input: A → Output: B"
Effect: Better response format and quality

Technique 4: Constraints
Add to system prompt: "Keep responses under 100 words"
Effect: Focused, concise answers
```

### Temperature Strategies
```
For factual accuracy:
- Set temperature 0.2-0.4
- Use system prompt emphasizing accuracy
- Ask for citations

For creativity:
- Set temperature 1.2-1.5
- Use system prompt encouraging imagination
- Ask for multiple options

For balanced use:
- Set temperature 0.7
- Generic system prompt
- Works well for most tasks
```

## 🐛 Troubleshooting

### Issue: "API Error: 401"
**Solution**: Check your API key is correct. Get new key from console.anthropic.com

### Issue: "Response Failed"
**Solution**: 
- Check internet connection
- Verify API key is valid
- Try with smaller max tokens
- Check account has credits

### Issue: "Conversation Lost"
**Solution**: Export chats before refreshing browser. Use "Export Chat" button.

### Issue: "Very Slow Responses"
**Solution**:
- Switch to Haiku model (faster)
- Reduce max tokens
- Close other tabs

## 📁 File Structure

```
advanced-llm-workspace/
├── index.html          # Main application
├── styles.css          # Styling
├── script.js           # Application logic
├── README.md           # This file
├── CONFIGURATION.md    # API and config details
├── ADVANCED_GUIDE.md   # Advanced usage guide
└── API_REFERENCE.md    # API endpoints reference
```

## 🔄 Version History

### v1.0 (Current)
- ✅ Three operation modes (Chat, Completion, Analysis)
- ✅ Multi-model support (Opus, Sonnet, Haiku)
- ✅ Advanced parameter control
- ✅ Token tracking and cost estimation
- ✅ Conversation export
- ✅ One-click presets
- ✅ Response formatting options
- ✅ Local API key storage

## 🚀 Future Enhancements

Planned features:
- [ ] Dark mode
- [ ] Multi-file upload support
- [ ] Conversation history in sidebar
- [ ] Custom system prompt library
- [ ] Conversation comparison
- [ ] Real-time token usage graph
- [ ] Batch processing
- [ ] Plugin system

## 📞 Support

### Getting Help
1. Check ADVANCED_GUIDE.md for usage questions
2. Review API_REFERENCE.md for technical details
3. See Troubleshooting section above

### Reporting Issues
- Check browser console for errors (F12)
- Verify API key is valid
- Try in different browser

## 📝 License

This project is open source and free to use, modify, and distribute.

## 🤝 Contributing

To improve this project:
1. Test features thoroughly
2. Report bugs with details
3. Suggest enhancements
4. Share your use cases

## 📚 Additional Resources

- [Anthropic Documentation](https://docs.anthropic.com)
- [Claude API Guide](https://docs.anthropic.com/en/docs/build-with-claude/overview)
- [Prompt Engineering Guide](https://docs.anthropic.com/en/docs/build-with-claude/prompt-engineering/overview)
- [Console](https://console.anthropic.com)

---

**Last Updated**: 2024  
**Maintained By**: Community  
**Status**: Active Development


good moring sir my slef ankush i am from gurugram haryna i am very hardable and senicer student i ensure you i  waill able to do work with you  
and never dispposnated be your attention i am very happay with your work  i have match but my jhatu team mate never do grid and always make excuse and thing that they become a espoarts payer jhantu  palayer i will play because no one konw what happend to with your life and sadden become somting and chnge your life ..now if they are not online thats show they are not prepare beacuse onne of thhem havvw one child 
