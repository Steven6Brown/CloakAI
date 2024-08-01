Locally Hosted AI Install & Setup Guide

Requirements
Hardware
  1.	Windows computer.
  2.	Computer with 8GB RAM or more.
  3.	Server for remote connectivity.
   
Software
  1.	Windows Subsystem for Linux (WSL).
  2.	Docker.
  3.	Ollama Llama 3.
  4.	Open WebUI.
  5.	Debian 12 or Ubuntu 24.04.
   
Additional Information
  1.	Data to train the model.
  2.	Access to the internet.
 
Commands
Setup WSL (Windows)
  1.	https://www.youtube.com/watch?v=Wjrdr0NU4Sk&t=158s
  2.	Install WSL and Ubuntu:
    a.	wsl --install
  3.	Connect to a WSL Instance in a new window:
    a.	wsl -d Ubuntu

Install Ollama Llama 3
  1.	Navigate to the Ollama download website:
    a.	https://ollama.com/download
  2.	Download Ollama:
    a.	curl -fsSL https://ollama.com/install.sh | sh
  3.	Add a model to Ollama:
    a.	ollama pull llama3

Install Docker
  1.	Add Docker's official GPG key:
    a.	https://docs.docker.com/engine/install/ubuntu/
    b.	sudo apt-get update
    c.	sudo apt-get install ca-certificates curl
    d.	sudo install -m 0755 -d /etc/apt/keyrings
    e.	sudo curl -fsSL https://download.docker.com/linux/ubuntu/gpg -o /etc/apt/keyrings/docker.asc
    f.	sudo chmod a+r /etc/apt/keyrings/docker.asc
  2.	Add the repository to Apt sources:
    a.	echo \
    b.	"deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/ubuntu \ $(. /etc/os-release && echo "$VERSION_CODENAME") stable" | \
    c.	sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
    d.	sudo apt-get update\
  3.	Install Docker:
    a.	sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin

Run Open WebUI Docker Container
  1.	To start and run the Docker Open WebUI container:
    a.	sudo docker run -d --network=host -p 8080:8080 --name <AI NAME> -v open-webui:/app/backend/data -e OLLAMA_BASE_URL=http://127.0.0.1:11434 --restart always ghcr.io/open-webui/open-webui:main

Install Prereqs & Pyenv (Optional)
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

Install Stable Diffusion (Optional)
  1.	Install command:
    a.	wget -q https://raw.githubusercontent.com/AUTOMATIC1111/stable-diffusion-webui/master/webui.sh
  2.	Make it executable:
    a.	chmod +x webui.sh
  3.	Run it:
    a.	./webui.sh --listen --api
 
Debian 12 Server Setup
https://www.youtube.com/watch?v=Wjrdr0NU4Sk&t=158s

Debian 12 Boot From ISO
  1.	ISO File:
    a.	asdafsfad

Install Ollama Llama 3
  1.	Navigate to the Ollama download website:
    a.	https://ollama.com/download
  2.	Download Ollama:
    a.	curl -fsSL https://ollama.com/install.sh | sh
  3.	Add a model to Ollama:
    a.	ollama pull llama3

Install Docker
  1.	Add Docker's official GPG key:
    a.	https://docs.docker.com/engine/install/debian/
    b.	sudo apt-get update
    c.	sudo apt-get install ca-certificates curl
    d.	sudo install -m 0755 -d /etc/apt/keyrings
    e.	sudo curl -fsSL https://download.docker.com/linux/ubuntu/gpg -o /etc/apt/keyrings/docker.asc
    f.	sudo chmod a+r /etc/apt/keyrings/docker.asc
  2.	Add the repository to Apt sources:
    a.	echo \
    b.	"deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/ubuntu \ $(. /etc/os-release && echo "$VERSION_CODENAME") stable" | \
    c.	sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
    d.	sudo apt-get update\
  3.	Install Docker:
    a.	sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin

Login Into GitHub From Console
  1.	Login Command:
    a.	sudo docker login ghcr.io
  2.	Username of Github.
  3.	GitHub token as password.

Pull Docker Image From GitHub
  1.	GitHub Repo:
    a.	https://github.com/Steven6Brown/CloakAI
  2.	Command:
    a.	sudo docker pull ghcr.io/steven6brown/cloakai/open-webui:latest
    b.	git clone https://github.com/steven6brown/cloakai

Run Open WebUI Docker Container
  1.	To start and run the Docker Open WebUI container:
    a.	sudo docker run -d --network=host -p 8080:8080 --name cloakai -v open-webui:/app/backend/data -e OLLAMA_BASE_URL=http://127.0.0.1:11434 --restart always ghcr.io/open-webui/open-webui:main
    b.	or
    c.	sudo docker run -d --network=host -p 8080:8080 --name cloakai -v open-webui:/app/backend/data -e OLLAMA_BASE_URL=http://127.0.0.1:11434 --restart always ghcr.io/steven6brown/cloakai/open-webui:latest

Connect To IP and Port
  1.	IP of server and then the port:
    a.	xxx.xxx.xx.xx:8080

Pull GitHub Folders With Data
  1.	GitHub Repo:
    a.	https://github.com/steven6brown/cloakai
 
Ubuntu 24.04 VM Server Setup
https://www.youtube.com/watch?v=Wjrdr0NU4Sk&t=158s

Install Ollama Llama 3
  1.	Navigate to the Ollama download website:
    a.	https://ollama.com/download
  2.	Download Ollama:
    a.	curl -fsSL https://ollama.com/install.sh | sh
  3.	Add a model to Ollama:
    a.	ollama pull llama3

Install Docker
  1.	Add Docker's official GPG key:
    a.	https://docs.docker.com/engine/install/ubuntu/
    b.	sudo apt-get update
    c.	sudo apt-get install ca-certificates curl
    d.	sudo install -m 0755 -d /etc/apt/keyrings
    e.	sudo curl -fsSL https://download.docker.com/linux/ubuntu/gpg -o /etc/apt/keyrings/docker.asc
    f.	sudo chmod a+r /etc/apt/keyrings/docker.asc
  2.	Add the repository to Apt sources:
    a.	echo \
    b.	"deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/ubuntu \ $(. /etc/os-release && echo "$VERSION_CODENAME") stable" | \
    c.	sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
    d.	sudo apt-get update\
  3.	Install Docker:
    a.	sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin

Login Into GitHub From Console
  1.	Login Command:
    a.	sudo docker login ghcr.io
  2.	Username of Github.
  3.	GitHub token as password.

Pull Docker Image From GitHub
  1.	GitHub Repo:
    a.	https://github.com/Steven6Brown/CloakAI
  2.	Command:
    a.	sudo docker pull ghcr.io/steven6brown/cloakai/open-webui:latest
    b.	git clone https://github.com/steven6brown/cloakai

Run Open WebUI Docker Container
  1.	To start and run the Docker Open WebUI container:
    a.	sudo docker run -d --network=host -p 8080:8080 --name cloakai -v open-webui:/app/backend/data -e OLLAMA_BASE_URL=http://127.0.0.1:11434 --restart always ghcr.io/open-webui/open-webui:main
    b.	or
    c.	sudo docker run -d --network=host -p 8080:8080 --name cloakai -v open-webui:/app/backend/data -e OLLAMA_BASE_URL=http://127.0.0.1:11434 --restart always ghcr.io/steven6brown/cloakai/open-webui:latest

Connect To IP and Port
  1.	IP of server and then the port:
    a.	xxx.xxx.xx.xx:8080

Pull GitHub Folders With Data
  1.	GitHub Repo:
    a.	https://github.com/steven6brown/cloakai
