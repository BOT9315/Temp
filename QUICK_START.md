# Quick Start Guide

Get up and running in 5 minutes. Detailed guides are available in README.md, ADVANCED_GUIDE.md, and API_REFERENCE.md.

## ⚡ 5-Minute Setup

### Step 1: Download (30 seconds)
- Download `advanced_llm_workspace.html`
- Save to your computer

### Step 2: Get API Key (2 minutes)
1. Visit https://console.anthropic.com
2. Sign up or log in
3. Go to API Keys
4. Cr
5. Copy the key (starts with `sk-ant-`)

### Step 3: Open Application (30 seconds)
- Double-click the HTML file
- It opens in your browser
- Click "Setup" button

### Step 4: Add API Key (1 minute)
1. Paste your API key
2. Click "Save & Continue"
3. Done!

### Step 5: Start Using (1 minute)
1. Choose a mode: Chat, Completion, or Analysis
2. Type your message
3. Click Send
4. Wait for response

## 🎯 First Tasks to Try

### Task 1: Chat Mode
```
Mode: Chat
Message: "Hello! What can you help me with?"
→ Learn what the AI can do

Message: "Can you explain quantum computing?"
→ Ask follow-up questions to build on response

Message: "Give me 3 real-world applications"
→ See how it remembers context
```

### Task 2: Completion Mode
```
Mode: Completion
Message: "Here's a recipe for chocolate chip cookies..."
→ See how it completes your text

Tip: Use "Preset → Creative" for more creative completions
```

### Task 3: Analysis Mode
```
Mode: Analysis
Paste this: "Machine learning is a subset of AI that enables 
computers to learn from data without being explicitly programmed. 
It's used in recommendation systems, image recognition..."

Message: "Summarize this in 1 sentence"
→ See focused analysis

Message: "What are the key applications mentioned?"
→ Extract specific information
```

## 🎚️ Try Different Settings

### Try Different Temperatures
```
Question: "Give me a creative name for a coffee shop"

Temperature 0.3:
- Conservative options
- "The Daily Brew"

Temperature 0.7 (Default):
- Balanced options
- "Bean There Coffee Co."

Temperature 1.5:
- Wild, creative options
- "Caffeinated Chronicles"
```

### Try Different Models
```
Same question: "Write a Python function to reverse a string"

Haiku (Fast & Cheap):
- Quick response
- Simple solution

Sonnet (Balanced):
- Good detail
- Reasonable speed

Opus (Most Capable):
- Most comprehensive
- Slowest response
```

## 💰 Check Your Token Usage

**How to see usage:**
- Left sidebar shows "Total Tokens Used"
- Shows estimated cost
- Updates after each response

**Example:**
- Total Tokens: 2,500
- Estimated Cost: $0.04 (at Sonnet 4.6 rates)

## 📤 Export Your First Chat

1. Have a conversation (at least 2 exchanges)
2. Click "Export Chat" button
3. File downloads as `.md`
4. Open in any text editor
5. Contains full conversation + timestamps

## 🆘 Common Issues

### Issue: "API Error: 401"
**Solution**: Check your API key
- Verify you copied the full key
- Make sure it starts with `sk-ant-`
- Generate a new key if needed

### Issue: Response Takes Long Time
**Solution**: Use faster model
- Switch to Haiku model
- Reduce max tokens
- Close other browser tabs

### Issue: "Not Enough API Credits"
**Solution**: Check your account
- Visit console.anthropic.com
- Check billing section
- Add payment method if needed

## 🚀 Next Steps

### After 5 Minute Setup

**Hour 1 - Basic Exploration**
- [ ] Try all three modes
- [ ] Test different temperatures
- [ ] Try all preset options
- [ ] Export a conversation

**Day 1 - Getting Comfortable**
- [ ] Create system prompts
- [ ] Work on a real task
- [ ] Read README.md for detailed info
- [ ] Monitor token usage

**Week 1 - Advanced Features**
- [ ] Read ADVANCED_GUIDE.md
- [ ] Try prompt engineering techniques
- [ ] Build a workflow
- [ ] Set optimization targets

## 📚 Documentation Map

**Quick Help**
- This file (Quick Start)
- FAQ below

**Detailed Info**
- README.md - Features, setup, usage
- ADVANCED_GUIDE.md - Power user techniques
- API_REFERENCE.md - Technical details
- CONFIGURATION.md - Setup and customization

## ❓ FAQ

### Q: Is my API key safe?
**A**: Yes! It's stored only in your browser's local storage. Never transmitted except to Anthropic's official API.

### Q: How much does it cost?
**A**: You pay per token. Sonnet 4.6 costs ~$0.003 per 1K input tokens and ~$0.015 per 1K output tokens.

### Q: Do you save my conversations?
**A**: No. Conversations are only stored in your browser. Export them manually to keep.

### Q: Can I use this offline?
**A**: No, it needs internet connection to reach Anthropic's API.

### Q: Which model should I use?
**A**: Start with Sonnet 4.6 (balanced). Use Opus for complex tasks, Haiku for quick tasks.

### Q: Can I change my API key?
**A**: Yes! Click "Change API Key" button in left sidebar.

### Q: What's the difference between modes?
**A**: Chat maintains memory, Completion generates text, Analysis focuses on content.

### Q: How do I clear my conversation?
**A**: Click "Clear Chat" button in left sidebar.

### Q: Can I access this on my phone?
**A**: Yes! Works on mobile browsers. Touch-friendly interface.

### Q: Is there a limit to conversations?
**A**: No. Limited only by your API budget.

### Q: Can I use this in production?
**A**: Yes! Use the backend proxy setup from CONFIGURATION.md for enterprise use.

## 🎓 Learning Resources

**To Learn More:**
- https://docs.anthropic.com - Official API docs
- https://console.anthropic.com - Your API dashboard
- README.md - Comprehensive guide
- ADVANCED_GUIDE.md - Expert techniques

## ⌚ Keyboard Shortcuts

| Shortcut | Action |
|----------|--------|
| Enter | Send message |
| Shift+Enter | New line in input |
| Ctrl+L | Focus on input |
| Cmd+K | Focus on input (Mac) |

## 🎯 Pro Tips for Beginners

1. **Read Error Messages**
   - They tell you what went wrong
   - Usually easy to fix

2. **Start Simple**
   - Don't use all features at once
   - Try one thing at a time

3. **Test Settings**
   - Same question with different temps
   - See what works best for you

4. **Track Tokens**
   - Watch token usage
   - Understand cost

5. **Save What Works**
   - Export good conversations
   - Create reusable prompts

6. **Ask for Help**
   - AI loves detailed questions
   - Provide context

7. **Iterate**
   - First draft rarely perfect
   - Ask for revisions

## 🚀 Ready to Go!

You now have everything you need to:
- ✅ Use the LLM Workspace
- ✅ Understand basic parameters
- ✅ Export conversations
- ✅ Try different models
- ✅ Monitor costs

**Start exploring!** Choose a mode above and begin your first conversation.

---

**Need detailed help?** Read README.md  
**Want advanced techniques?** Read ADVANCED_GUIDE.md  
**Technical questions?** Read API_REFERENCE.md
