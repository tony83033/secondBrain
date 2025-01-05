reference = https://github.com/krishnaik06/Crew-AI-Crash-course/blob/main/crew.py
I create an ai agent using crew ai 
for embeding I use google embeding because ollama embeding was giving some problem 
(# unexpected keyword argument 'task_type' in crewai tools config
https://github.com/crewAIInc/crewAI/issues/1295
) but when using google embeding not getting this error


also getting some error on py tube 
https://github.com/pytube/pytube

so fix by modifying the code of pytube in main.py
innertube = InnerTube(client='WEB',use_oauth=self.use_oauth, allow_cache=self.allow_oauth_cache)

added client="WEB" and it start working fine find this fix in a githug issue section 


for model we can use ollama mode for now I am using chatopenai from langchain to create llm of ollama 



now I am getting some random error on open ai auth

 File "C:\Users\HP\Desktop\25Year\.venv\Lib\site-packages\litellm\litellm_core_utils\exception_mapping_utils.py", line 389, in exception_type
    raise AuthenticationError(
litellm.exceptions.AuthenticationError: litellm.AuthenticationError: AuthenticationError: OpenAIException - Error code: 401 - {'error': {'message': 'Incorrect API key provided: NA. You can find your API key at https://platform.openai.com/account/api-keys.', 'type': 'invalid_request_error', 'param': None, 'code': 'invalid_api_key'}}

========================================================

thinking to run ollama with better model on googel shell -> to do 

also thinking to only use langchain insted of 
