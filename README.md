# -AI-Story



This code uses OpenAI's API to generate a story based on a given prompt. 

import openai -----#This line imports the OpenAI Python module.

openai.api_key = "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"--------#The API key for the OpenAI module, allowing it to authenticate with OpenAI's servers.

def generate_story(prompt):  ----# defines a function called generate_story that takes a single argument prompt.

model_engine = "text-davinci-002"    # the model engine to use for generating the story. In this case, it is set to "text-davinci-002", which is a language model that                                          OpenAI has trained.

    response = openai.Completion.create(
        engine=model_engine,
        prompt=prompt,
        max_tokens=1024,
        n=1,
        stop=None,
        temperature=0.5,
    )    --------------------------#Sends a request to OpenAI's servers to generate a story based on the given prompt. The Completion.create() method takes several arguments, including the model engine to use, the prompt to use for generating the story, the maximum number of tokens to generate (in this case, 1024), the number of responses to generate (in this case, 1), a list of stop sequences (in this case, None), and the "temperature" to use for generating the story. The temperature controls the randomness and creativity of the generated text.
    
        story = response.choices[0].text.strip()
    return story------------------------#extracts the generated story from the response object and returns it as a string
    
    
    story = generate_story("Write a story about a time traveler who goes back to the 1920s and meets a famous author.")
print(story)-------------------------------------# calls the generate_story() function with the prompt "Write a story about a time traveler who goes back to the 1920s and meets a famous author." and prints the resulting story to the console.




