

from dotenv import load_dotenv
import os


load_dotenv(override=True)

openai_api_key = os.getenv('OPENAI_API_KEY')

from openai import OpenAI
openai = OpenAI()

question = "Can you list jobs or professions that are least likely to be replaced by AI in the near future?"
messages = [{"role": "user", "content": question}]
