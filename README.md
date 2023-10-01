# LLM
Read "A hacker's guide to Language Models" by Jeremy Howard.

### pip install openplayground
### openplayground run

Or build Docker for it:
###docker build . --tag "openplayground"
###docker run --name openplayground -p 5432:5432 -d --volume openplayground:/web/config openplayground
### 

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
