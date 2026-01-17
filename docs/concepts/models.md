# Model Selection

Choose the right Gemini model for your task.

## Available Models

### Gemini-3-flash-preview (Default)
- **Best for**: General-purpose tasks, balanced performance
- **Context**: Large context window
- **Use when**: Default choice for most tasks, good balance of speed and capability

### Gemini-3-pro-preview
- **Best for**: Complex reasoning, advanced analysis
- **Context**: Large context window
- **Use when**: Tasks requiring deeper reasoning and more sophisticated responses

### Gemini-2.5-pro
- **Best for**: Complex analysis, large codebases
- **Context**: 2M tokens
- **Use when**: Analyzing entire projects, architectural reviews, stronger reasoning

### Gemini-2.5-flash
- **Best for**: Quick responses, routine tasks
- **Context**: 1M tokens
- **Use when**: Fast code reviews, Analyzing entire projects, simple explanations

## Setting Models
```bash
You need use natural language: "...using gemini flash"
```
```bash
You can also append with '-m' or ask specifically with 
```

### In Configuration
```json
{
  "mcpServers": {
    "gemini-cli": {
      "command": "gemini-mcp",
      "env": {
        "GEMINI_MODEL": "gemini-1.5-flash"
      }
    }
  }
}
```

### Per Request (Coming Soon)
```
/gemini-cli:analyze --model=flash @file.js quick review
```

## Model Comparison

| Model | Speed | Context | Best Use Case |
|-------|-------|---------|---------------|
| gemini-3-flash-preview | Fast | Large | Default, general tasks |
| gemini-3-pro-preview | Moderate | Large | Complex reasoning |
| gemini-2.5-pro | Slower | 2M tokens | Big ideas, architecture |
| gemini-2.5-flash | Fast | 1M tokens | Quick, specific changes |

## Cost Optimization

1. **Start with gemini-3-flash-preview** (default) for most tasks
2. **Use gemini-3-pro-preview** for complex reasoning
3. **Use gemini-2.5-pro** when you need the full 2M context

## Token Limits

- **Pro**: ~2 million tokens (~500k lines of code)
- **Flash**: ~1 million tokens (~250k lines of code)
- **Flash-8B**: ~1 million tokens (~250k lines of code)

## Recommendations

- **Code Review**: gemini-3-flash-preview (default)
- **Architecture Analysis**: gemini-3-pro-preview or gemini-2.5-pro
- **Quick Fixes**: gemini-3-flash-preview
- **Documentation**: gemini-3-flash-preview
- **Security Audit**: gemini-3-pro-preview or gemini-2.5-pro