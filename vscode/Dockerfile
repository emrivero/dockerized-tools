FROM ubuntu:18.04

RUN apt-get update -y && apt-get install wget gpg -y
RUN wget -qO- https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > packages.microsoft.gpg 
RUN install -o root -g root -m 644 packages.microsoft.gpg /etc/apt/trusted.gpg.d/
RUN sh -c 'echo "deb [arch=amd64,arm64,armhf signed-by=/etc/apt/trusted.gpg.d/packages.microsoft.gpg] https://packages.microsoft.com/repos/code stable main" > /etc/apt/sources.list.d/vscode.list'
RUN rm -f packages.microsoft.gpg
RUN apt-get install apt-transport-https -y
RUN apt-get update -y
RUN apt-get install code -y
RUN apt install libxshmfence1 libglu1 libasound2-dev -y
ENV DONT_PROMPT_WSL_INSTALL 1