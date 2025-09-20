# Lab 2 with Deepseek Configuration

This notebook (`2_lab2_deepseek.ipynb`) is a modified version of the original Lab 2 that uses Deepseek instead of OpenAI.

## Changes Made

### 1. Updated Imports

- Added `OpenAIChatCompletionsModel` import from agents
- Added `AsyncOpenAI` import from openai
- Added Deepseek configuration code

### 2. Deepseek Configuration

```python
# Configure Deepseek
DEEPSEEK_BASE_URL = "https://api.deepseek.com/v1"
deepseek_api_key = os.getenv("DEEPSEEK_API_KEY")
deepseek_client = AsyncOpenAI(base_url=DEEPSEEK_BASE_URL, api_key=deepseek_api_key)
deepseek_model = OpenAIChatCompletionsModel(model="deepseek-chat", openai_client=deepseek_client)
```

### 3. Model References

All instances of `model="gpt-4o-mini"` have been replaced with `model=deepseek_model` throughout the notebook.

## Setup Requirements

1. **Deepseek API Key**: You need to get an API key from [Deepseek Platform](https://platform.deepseek.com/)
2. **Environment Variable**: Add `DEEPSEEK_API_KEY=your_api_key_here` to your `.env` file
3. **Initial Balance**: Deepseek requires a minimum $2 upfront balance

## Benefits of Using Deepseek

- **Cost Effective**: Significantly cheaper than OpenAI models
- **Good Performance**: Deepseek-chat is a capable model for agent tasks
- **OpenAI Compatible**: Uses the same API format as OpenAI

## Usage

1. Make sure your `.env` file contains:

   ```
   DEEPSEEK_API_KEY=your_deepseek_api_key
   SENDGRID_API_KEY=your_sendgrid_api_key
   ```

2. Run the notebook cells as you would with the original version

3. The functionality remains exactly the same - only the underlying model has changed

## Notes

- The notebook maintains all the original functionality for sales email generation
- All agent interactions, tools, and handoffs work the same way
- The trace functionality will still work with OpenAI's platform
- Performance may vary slightly due to different model characteristics

## Troubleshooting

If you encounter issues:

1. Verify your Deepseek API key is correct
2. Check that you have sufficient balance in your Deepseek account
3. Ensure all environment variables are properly set
4. The SSL certificate fixes mentioned in the original notebook may still be needed


