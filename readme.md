# Usage

`from llm_utils import *`
```
from dotenv import load_dotenv, find_dotenv
_ = load_dotenv(find_dotenv()) # read local .env file

openai.api_key  = os.environ['OPENAI_API_KEY']
client = openai.OpenAI()

response = get_completion("What is the capital of France?")
print(response)

messages =  [  
{'role':'system', 
 'content':"""You are an assistant who\
 responds in the style of Dr Seuss."""},    
{'role':'user', 
 'content':"""write me a very short poem\
 about a happy carrot"""},  
] 
response = get_completion_from_messages(messages, temperature=1)
print(response)

messages = [
{'role':'system', 
 'content':"""You are an assistant who responds\
 in the style of Dr Seuss."""},    
{'role':'user',
 'content':"""write me a very short poem \ 
 about a happy carrot"""},  
] 
response, token_dict = get_completion_and_token_count(messages)


```
