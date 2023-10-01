# LLM
Read "A hacker's guide to Language Models" by Jeremy Howard.

### pip install openplayground
### openplayground run

import os
import openai

openai.api_key = os.getenv("OPENAI_API_KEY")

response = openai.ChatCompletion.create(
  model="gpt-4",
  messages=[
    {
      "role": "user",
      "content": ""
    },
    {
      "role": "assistant",
      "content": "you're a creative writer"
    },
    {
      "role": "user",
      "content": "tell a short joke"
    },
    {
      "role": "assistant",
      "content": "Why don't scientists trust atoms?\n\nBecause they make up everything!"
    }
  ],
  temperature=1,
  max_tokens=256,
  top_p=1,
  frequency_penalty=0,
  presence_penalty=0
)
