Thus begins the chronicles of Dooracle; a fledgling digital product startup set to revolutionize the fortune telling industry.  

Their moonshot? 

To build a fortune-telling chatbot.  

The project is aimed at filling the demand for people who want their futures predicted. 

When the superintelligent AI is finally ready for transfer learning, their product will be there.  

A bulletproof plan.  

## Step by Step NLP: Data to Deployment
[A workshop on how to build and deploy a virtual chatbot using Natural Language Processing](https://www.eventbrite.com/e/step-by-step-natural-language-processing-workshop-from-data-to-deployment-tickets-201001560077)
You can check out the slide [here](https://docs.google.com/presentation/d/140d_Rab-Tt8dpBN-DQmQeoY2LG7LCFiA/edit)

📹👇
[![Design_YT_DLAIEventBrite](https://user-images.githubusercontent.com/72572922/142292687-fe562668-fdbf-4028-9aa8-62ee5cb4c86c.PNG)](https://youtu.be/D9hY8pZe7hk)

After the event, we heard your feedback!  Greg created a step by step walkthrough, complete with stumbles and rewinds, that takes about 75 minutes to see everything about what happens behind the scenes.
[![FullRunThrough (Time 0_10_41;01)_small](https://user-images.githubusercontent.com/72572922/142295578-41cf946b-8c70-481e-9247-97aafb1e88bf.png)](https://youtu.be/cQzqaKw5y2I)


## How To Use These Videos
The following videos were part of original workshop, and will help you to deploy the [DialoGPT-medium](https://huggingface.co/microsoft/DialoGPT-medium) chatbot to your local machine or to the cloud.  

### Prerequisites
These videos were shot on a Windows machine running [Ubuntu](https://www.microsoft.com/en-us/p/ubuntu/9nblggh4msv6?activetab=pivot:overviewtab) on [WSL2](https://docs.microsoft.com/en-us/windows/wsl/install) through [Windows Terminal](https://www.microsoft.com/en-us/p/windows-terminal/9n0dx20hk701#activetab=pivot:overviewtab).  [Google Cloud Platform](https://cloud.google.com/) was used to deploy the chatbot remotely.  [Docker Desktop](https://www.docker.com/products/docker-desktop) was also leveraged along with [Notepadd++](https://notepad-plus-plus.org/downloads/) 


### Part 1: Get Chatbot Running on Virtual Machine in Jupyter Notebook
[![GetGPTRunning (Time 0_00_20;05)](https://user-images.githubusercontent.com/72572922/142128311-fbd624f5-fdc2-4aeb-b3e5-4f8c48849b03.png)](https://youtu.be/VHMBDBdwTY0)

#### Install packages in WSL2 Ubuntu Root
```
sudo apt update
sudo apt install python3-pip python3-dev
sudo -H pip3 install --upgrade pip
sudo -H pip3 install virtualenv
```

#### Allocate folders and create vm
```
mkdir ~/chatbot-event
cd chatbot-event
virtualenv chattyvm
source chattyvm/bin/activate
```
#### Install libraries
```
pip install jupyter
pip install torch
pip install transformers
```
### Then just run DialoGPT in Jupyter!

### Part 2: Open-Source Chatbot UI and DialoGPT Intelligence Upgrade
[![GothamChatbotRunning (Time 0_03_43;22)](https://user-images.githubusercontent.com/72572922/142130786-e8b12f65-df49-4f37-990e-f0943b0fe190.png)](https://youtu.be/JRAIZeZ7IfA)

#### Install git and clone this repo!
```
sudo apt install git
git clone https://github.com/FourthBrain/step-by-step-nlp-dialogpt-chatbot.git
```

#### Run it!
```
cd step-by-step-nlp-dialogpt-chatbot/dialogpt-chatbot
flask run
```

### Part 3: Dockerizing DialoGPT Chatbot
[![DialoGPTRunningOnDocker (Time 0_02_11;12)](https://user-images.githubusercontent.com/72572922/142128807-d42789de-bafc-4412-b1a5-9e31f8b15fa8.png)](https://youtu.be/Bl0fRQ5_XqA)

#### Install git and clone this repo!
```
sudo apt install git
git clone https://github.com/FourthBrain/step-by-step-nlp-dialogpt-chatbot.git
```

#### Run it!
```
cd ..
cd dialogpt-chatbot-dockerize
docker build -t dialogpt-chatbot-image
docker run -d -p 8080:8080 dialogpt-chatbot-image
```

### Part 4: Deploying DialoGPT in the Cloud
[![DialoGPTRunningOnGCP (Time 0_03_29;04)](https://user-images.githubusercontent.com/72572922/142128920-2fd5646d-03a1-4c03-a3eb-0848e1a10f7b.png)](https://youtu.be/jPfQv8hh_pw)

#### Create account, setup billing, open terminal, upload files
```
cd dialogpt-chatbot-dockerize
gcloud builds submit --tag gcr.io/my-project/dialogpt-chatbot-image
gcloud run deploy --image gcr.io/my-project/dialogpt-chatbot-image --memory 4Gi
```

# Shoutouts 
Big ups to Hugging Face for their awesome repo of models and streamlining all things SOTA ML modeling; you can check out DialoGPT-medium [here](https://huggingface.co/microsoft/DialoGPT-medium)

Thanks to [bhargavramdr](https://github.com/bhargavramdr) for the [right chatbot UI](https://github.com/bhargavramdr/Gotham-chatbot) at the right time.  Happy Halloween 2021! 

# License
All source from FourthBrain is free to use, but microsoft/DialoGPT is licensed under the MIT License.
