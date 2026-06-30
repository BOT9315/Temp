# API Reference Guide
........
Complete technical documentation for the LLM Workspace's API integration with Anthropic Claude.

## 📡 API Endpoints

### Primary Endpoint
```
POST https://api.anthropic.com/v1/messages
```
### Authentication
```
Header: x-api-key: YOUR_API_KEY
Header: anthropic-version: 2023-06-01
Header: Content-Type: application/json
```

## 📤 Request Format

### Complete Request Example
```javascript
{
  "model": "claude-sonnet-4-6",
  "max_tokens": 1024,
  "temperature": 0.7,
  "top_p": 0.9,
  "system": "You are a helpful assistant",
  "messages": [
    {
      "role": "user",
      "content": "Hello, how are you?"
    },
    {
      "role": "assistant",
      "content": "I'm doing well, thank you for asking!"
    },
    {
      "role": "user",
      "content": "What's the weather like?"
    }
  ]
}
```

### Request Parameters

| Parameter | Type | Range | Required | Description |
|-----------|------|-------|----------|-------------|
| `model` | string | - | ✅ | Model ID (claude-opus-4-6, claude-sonnet-4-6, claude-haiku-4-5) |
| `max_tokens` | integer | 1-4096 | ✅ | Maximum output tokens |
| `messages` | array | - | ✅ | Array of message objects |
| `temperature` | float | 0.0-2.0 | ❌ | Randomness (default: 1.0) |
| `top_p` | float | 0.0-1.0 | ❌ | Nucleus sampling (default: 1.0) |
| `system` | string | - | ❌ | System prompt/instructions |

### Message Object Format
```javascript
{
  "role": "user",              // "user" or "assistant"
  "content": "Your message"    // The actual message text
}
```

## 📥 Response Format

### Successful Response (200 OK)
```javascript
{
  "id": "msg_1234567890",
  "type": "message",
  "role": "assistant",
  "content": [
    {
      "type": "text",
      "text": "Response content here"
    }
  ],
  "model": "claude-sonnet-4-6",
  "stop_reason": "end_turn",
  "stop_sequence": null,
  "usage": {
    "input_tokens": 123,
    "output_tokens": 456
  }
}
```

### Response Fields

| Field | Type | Description |
|-------|------|-------------|
| `id` | string | Unique message ID |
| `type` | string | Always "message" |
| `role` | string | Always "assistant" |
| `content` | array | Array of content blocks |
| `content[0].type` | string | "text" for text responses |
| `content[0].text` | string | The actual response |
| `model` | string | Model used |
| `stop_reason` | string | "end_turn" or "max_tokens" |
| `usage.input_tokens` | integer | Tokens in your prompt |
| `usage.output_tokens` | integer | Tokens in response |

### Error Response (400, 401, 429, 500)
```javascript
{
  "type": "error",
  "error": {
    "type": "invalid_request_error",
    "message": "Error description"
  }
}
```

### Common Error Codes

| Code | Type | Cause | Solution |
|------|------|-------|----------|
| 400 | invalid_request_error | Bad request format | Check JSON syntax |
| 401 | authentication_error | Invalid API key | Verify API key |
| 429 | rate_limit_error | Too many requests | Wait before retrying |
| 500 | server_error | API server issue | Retry later |

## 🎯 Model Specifications

### Claude Opus 4.6
- **Capability**: Most advanced, best reasoning
- **Speed**: Slower
- **Cost**: Higher ($15/$75 per 1M input/output tokens)
- **Best for**: Complex tasks, reasoning, analysis
- **Context Window**: 200K tokens
- **Latency**: Higher (~2-5 seconds)

```javascript
{
  "model": "claude-opus-4-6",
  "max_tokens": 4096,
  "temperature": 0.5  // More deterministic for reasoning
}
```

### Claude Sonnet 4.6
- **Capability**: Balanced performance
- **Speed**: Medium
- **Cost**: Medium ($3/$15 per 1M input/output tokens)
- **Best for**: Most general tasks
- **Context Window**: 200K tokens
- **Latency**: Medium (~1-3 seconds)

```javascript
{
  "model": "claude-sonnet-4-6",
  "max_tokens": 1024,
  "temperature": 0.7  // Good for variety
}
```

### Claude Haiku 4.5
- **Capability**: Lightweight, focused
- **Speed**: Fastest
- **Cost**: Cheapest ($0.80/$4 per 1M input/output tokens)
- **Best for**: Simple tasks, high volume
- **Context Window**: 200K tokens
- **Latency**: Lowest (~200-500ms)

```javascript
{
  "model": "claude-haiku-4-5",
  "max_tokens": 512,
  "temperature": 0.7
}
```

## 🧮 Token Counting

### How Tokens Work
- ~1 token ≈ 4 characters
- ~1 token ≈ 0.75 words
- System prompt counts toward total
- Each message separately processed

### Estimation Formula
```
Tokens ≈ Character Count / 4
Cost = (Input Tokens * Input Rate + Output Tokens * Output Rate) / 1,000,000
```

### Example Calculation
```
Input text: "Hello, how are you?" (20 characters)
Estimated tokens: 20 / 4 = 5 tokens

System prompt: 100 characters
Estimated tokens: 100 / 4 = 25 tokens

Response: 400 characters
Estimated tokens: 400 / 4 = 100 tokens

Total with Sonnet 4.6:
- Input: (20 + 100) / 4 = 30 tokens × $3/1M = $0.00009
- Output: 100 tokens × $15/1M = $0.0015
- Total cost: ~$0.0016
```

## 🔧 Parameter Tuning Guide

### Temperature Tuning by Task
```
Task: Factual Q&A
- Temperature: 0.2-0.4
- Top-P: 0.7-0.8
- Reason: Consistency is critical

Task: Creative Writing
- Temperature: 1.0-1.5
- Top-P: 0.9-0.95
- Reason: Variety and creativity

Task: Code Generation
- Temperature: 0.3-0.6
- Top-P: 0.8-0.9
- Reason: Correctness is important

Task: Brainstorming
- Temperature: 1.3-1.8
- Top-P: 0.95-1.0
- Reason: Maximum diversity needed

Task: Translation
- Temperature: 0.2-0.4
- Top-P: 0.7-0.8
- Reason: Accuracy is critical
```

### Max Tokens by Use Case
```
Use Case: Chat response
- Recommended: 300-500 tokens
- Range: 100-1000

Use Case: Code generation
- Recommended: 800-2000 tokens
- Range: 500-4000

Use Case: Article/essay
- Recommended: 1500-3000 tokens
- Range: 1000-4000

Use Case: Summary
- Recommended: 200-400 tokens
- Range: 100-800

Use Case: Quick answer
- Recommended: 100-300 tokens
- Range: 50-500
```

## 🔄 Streaming API

For real-time streaming responses (advanced):

```javascript
const response = await fetch('https://api.anthropic.com/v1/messages/stream', {
  method: 'POST',
  headers: {
    'x-api-key': apiKey,
    'anthropic-version': '2023-06-01',
    'Content-Type': 'application/json'
  },
  body: JSON.stringify({
    model: 'claude-sonnet-4-6',
    max_tokens: 1024,
    messages: [{ role: 'user', content: 'Hello!' }]
  })
});

// Process streaming events
const reader = response.body.getReader();
while (true) {
  const { done, value } = await reader.read();
  if (done) break;
  
  const text = new TextDecoder().decode(value);
  const lines = text.split('\n');
  
  for (const line of lines) {
    if (line.startsWith('data: ')) {
      const event = JSON.parse(line.slice(6));
      if (event.type === 'content_block_delta') {
        console.log(event.delta.text);
      }
    }
  }
}
```

## 🔐 Rate Limiting

### Limits (as of 2024)
- **Free tier**: 5 requests per minute, 10K tokens per day
- **Paid tier**: Depends on account, typically 1000+ req/min

### Rate Limit Headers
```
x-ratelimit-limit-requests: 1000
x-ratelimit-limit-tokens: 100000
x-ratelimit-remaining-requests: 999
x-ratelimit-remaining-tokens: 99500
x-ratelimit-reset-requests: 2024-01-01T12:00:00Z
x-ratelimit-reset-tokens: 2024-01-01T12:01:00Z
```

### Handling Rate Limits
```javascript
if (response.status === 429) {
  const resetTime = response.headers.get('x-ratelimit-reset-requests');
  const waitTime = new Date(resetTime) - new Date();
  console.log(`Rate limited. Wait ${waitTime}ms before retry`);
  
  // Exponential backoff
  setTimeout(() => retryRequest(), waitTime);
}
```

## 📋 System Prompt Examples

### Expert Role
```
You are a senior software architect with 20 years of experience.
You provide detailed, production-ready solutions.
Always explain trade-offs and best practices.
Use industry standards and established patterns.
```

### Educational Role
```
You are an experienced teacher explaining complex topics.
Break down concepts into simple, understandable parts.
Use analogies and examples.
Encourage critical thinking.
Avoid jargon unless necessary.
```

### Analysis Role
```
You are a data analyst specializing in insights extraction.
Focus on factual, evidence-based analysis.
Identify patterns and correlations.
Provide actionable recommendations.
Always cite sources when applicable.
```

### Creative Role
```
You are a creative writer with a distinctive voice.
Generate imaginative, engaging content.
Take creative risks and explore unique angles.
Use vivid language and interesting metaphors.
Push boundaries while remaining coherent.
```

## ✅ Integration Checklist

- [ ] API key obtained and securely stored
- [ ] Endpoint URLs verified
- [ ] Request format tested
- [ ] Response handling implemented
- [ ] Error handling in place
- [ ] Rate limiting handled
- [ ] Token counting implemented
- [ ] Cost tracking enabled
- [ ] Logging for debugging
- [ ] User feedback mechanisms
- [ ] Timeout handling
- [ ] Retry logic implemented

## 🚀 Best Practices

### DO
✅ Store API key in environment variables or secure storage  
✅ Implement retry logic with exponential backoff  
✅ Monitor token usage and costs  
✅ Validate user input before sending  
✅ Set appropriate timeouts  
✅ Log errors for debugging  
✅ Use streaming for long responses  
✅ Test with different models  

### DON'T
❌ Expose API key in client-side code  
❌ Make unlimited requests without rate limiting  
❌ Send excessively long prompts  
❌ Ignore error responses  
❌ Cache responses indefinitely  
❌ Send sensitive data without encryption  
❌ Use production API keys for testing  
❌ Overload with concurrent requests  

---

**API Version**: 2023-06-01  
**Last Updated**: 2024  
**Status**: Current & Active
