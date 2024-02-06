## Folder guide
1. **techfest-frontend-main folder** contains code for frontend in react created by @KZY20112001
3. **ai_models folder** contains code files for ai_models, LLMv3 file created by @uigure generates sentences required for image generation, music generation and poster generation in Asset_Generation file created by @leongseng99. Asset_Generation file generates the required assets for the frontend. The code files are in ipynb to show that the output corresponds with the demo video.
   
## Inspiration
Reference Code 5E
With 16 ministries and over 50 statutory boards, the traditional storyboarding process for government policy communication can be time consuming and challenging. With newer policies coming out at an increased rate to address the changes in economic conditions and challenges in Singapore, it is essential that the creative minds behind policy communication are able to communicate these newer policies to the general public quickly and effectively. The recent advances in AI for text generation, Image generation and Audio generation have inspired us to leverage on these tools to assist in the traditional storyboarding process 

## What it does
ASAP GPT prioritizes safety and data integrity, leveraging on offline-open source models to handle sensitive government policies securely. The user only needs to cut and paste the content of the policy to ASAP GPT to access all of ASAP GPT's features. ASAP GPT's features cater to both seasoned creators and newcomers, offering Large Language Model support to generate scripts for scenes and narration, image-based storyboard assistance for efficiency, and music recommendations for added depth in storytelling. ASAP GPT even provides a concept video introduction to elevate the overall storyboarding experience. 

The transformative benefits of ASAP GPT are evident in its ability to dramatically reduce the time required for creating storyboards, allowing professionals to focus on the more strategic and creative facets of policy communication. The automated nature assists in consistent quality, crucial for maintaining a unified visual representation of government policies. Cost-effectiveness is another highlight, with savings in time and resources translating into reduced expenses for organizations involved in policy communication.

## How we built it
1. **Text generation**: TheBloke/CapybaraHermes-2.5-Mistral-7B-GGUF LLM with prompt engineering and post processing to generate scenes, storyboard, music genre, title and tagline of poster.
2. **Image generation**: After receiving the various strings from the LLM, subsequent various models are used for different tasks.
3. **Base image generation**: Stabilityai/stble-diffusion-2 will use the respective sentence to generate images of each scene. 
4. **Refine of image**: ruyaway/stable-ddiffusion-v1-5 is used to improve the image by giving the model base image and additional prompt to configure it to warm colour and detail and 8k resolution.
5. **Music Selection**: facebook/musicgen-small is used to generate the audio using the music genre prompt.
6. **AI voiceover**: Google Text-to-Speech  is used for the summary, it is then concated using cv2 os with video and music.
7. **Poster generation**: stability/stable-diffusion-x1-base-1.0 is used for poster generation using the title and tagline prompt.
8. **Frontend**: ReactJS

## Challenges we ran into
1. Tried to use API for AI models, however almost all API we came across requires payment.
2. GPU is required to run the locally stored AI models.
3. Prompt engineering is difficult, a bad prompt leads to inconsistent quality of results.

## Accomplishments that we're proud of
1. Came up with an idea for the pipeline to achieve the desired results.
2. Able to work as a team and split the workload to research and implement in a short amount of time.

## What we learned
1. How to use huggingface
2. How to implement AI models from huggingface

## What's next for Team_55_ASAPGPT
**Explore different usecases of AI for public good!** :smile:
