
*🔐 1. Load Environment Variables*

from dotenv import load_dotenv
import os

# Load variables from .env file (e.g. your OpenAI API key)
load_dotenv(override=True)
openai_api_key = os.getenv('OPENAI_API_KEY')


*🤖 2. Initialize OpenAI Client*
from openai import OpenAI

# Create an OpenAI client instance
openai = OpenAI()

*💬 3. Define the User Question*

# The prompt/question to ask the model
question = "Can you list jobs or professions that are least likely to be replaced by AI in the near future?"
messages = [{"role": "user", "content": question}]


*🧠 4. Call the Chat Completion API*

# Send the request to the OpenAI Chat API using GPT-4o-mini
response = openai.chat.completions.create(
    model="gpt-4o-mini",
    messages=messages
)


*📤 5. Extract and Display the Answer*

# Extract and print the model's answer
answer = response.choices[0].message.content
print(answer)

*📄 6. Display Answer in Markdown (Jupyter Notebook)*

# Nicely display the model's response using Markdown formatting
from IPython.display import Markdown, display
display(Markdown(answer))
