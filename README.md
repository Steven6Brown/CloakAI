Locally Hosted AI Install & Setup Guide

Table of Contents
Requirements
Hardware
Software
Additional Information
Commands
Setup WSL (Windows)
Install Ollama Llama 3
Install Docker
Run Open WebUI Docker Container
Install Prereqs & Pyenv
Install Stable Diffusion
Setup

 
Requirements

  Hardware
    1.	Windows computer.
    2.	Computer with 8GB RAM or more.
  Software
    1.	Windows Subsystem for Linux (WSL).
    2.	Docker.
    3.	Ollama Llama 3.
    4.	Open WebUI.
  Additional Information
    1.	Data to train the model.
    2.	Access to internet.

 
Commands
Setup WSL (Windows)
  1.	Install WSL and Ubuntu:
    a.	wsl --install
  2.	Connect to a WSL Instance in a new window:
    a.	wsl -d Ubuntu


Setup Ubuntu 24.04
  1.	Navigate to the GitHub to pull docker image:
    a.	https://github.com/Steven6Brown?tab=packages
  2.	On the VM – run the pull command:
    a.	sudo docker pull ghcr.io/steven6brown/cloakai/open-webui:latest


Install Ollama Llama 3
  3.	Navigate to the Ollama download website:
    a.	https://ollama.com/download
  4.	Download Ollama:
    a.	curl -fsSL https://ollama.com/install.sh | sh
  5.	Add a model to Ollama:
    a.	ollama pull llama3


Install Docker
  1.	Add Docker's official GPG key:
    a.	sudo apt-get update
    b.	sudo apt-get install ca-certificates curl
    c.	sudo install -m 0755 -d /etc/apt/keyrings
    d.	sudo curl -fsSL https://download.docker.com/linux/ubuntu/gpg -o /etc/apt/keyrings/docker.asc
    e.	sudo chmod a+r /etc/apt/keyrings/docker.asc
  2.	Add the repository to Apt sources:
    a.	echo \
    b.	"deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/ubuntu \ $(. /etc/os-release && echo "$VERSION_CODENAME") stable" | \
    c.	sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
    d.	sudo apt-get update\
  
  3.	Install Docker:
    a.	sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin

Run Open WebUI Docker Container
  1.	To start and run the Docker Open WebUI container:
    a.	sudo docker run -d --network=host -v open-webui:/app/backend/data -e OLLAMA_BASE_URL=http://127.0.0.1:11434 --name open-webui --restart always ghcr.io/open-webui/open-webui:main


Install Prereqs & Pyenv
  1.	Required:
  a.	Prereqs
  b.	Pyenv
  2.	Install prereqs:
  a.	sudo apt install -y make build-essential libssl-dev zlib1g-dev \ libbz2-dev libreadline-dev libsqlite3-dev wget curl llvm libncurses5-dev \ libncursesw5-dev xz-utils tk-dev libffi-dev liblzma-dev git
  3.	Install Pyenv:
  a.	curl https://pyenv.run | bash
  4.	Install Python 3.10:
  a.	pyenv install 3.10
  5.	Make it global:
  a.	pyenv global 3.10


Install Stable Diffusion
  1.	Install command:
    a.	wget -q https://raw.githubusercontent.com/AUTOMATIC1111/stable-diffusion-webui/master/webui.sh
  2.	Make it executable:
    a.	chmod +x webui.sh
  3.	Run it:
    a.	./webui.sh --listen --api
   
Setup
  https://www.youtube.com/watch?v=Wjrdr0NU4Sk&t=158s

Access from another computer:
  1.	Set inbound firewall rule – allow TCP 8080 traffic on public and private networks
  2.	Enable ufw
  3.	Install and pull docker image on server side.
  4.	Connect to IP address of server then the port number:
    a.  xxx.xxx.xx.xx:8080


![image](https://github.com/user-attachments/assets/73587a3b-7964-4796-8edd-13a762a84af5)
