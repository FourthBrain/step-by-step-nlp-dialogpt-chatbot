# Deploy Flask App Locally in a Docker Container

## Quick Setup - watch the video and follow the steps!
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
