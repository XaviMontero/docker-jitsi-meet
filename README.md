# Jitsi Meet on Docker

![](resources/jitsi-docker.png)

[Jitsi](https://jitsi.org/) is a set of Open Source projects that allows you to easily build and deploy secure videoconferencing solutions.

[Jitsi Meet](https://jitsi.org/jitsi-meet/) is a fully encrypted, 100% Open Source video conferencing solution that you can use all day, every day, for free — with no account needed.

This repository contains the necessary tools to run a Jitsi Meet stack on [Docker](https://www.docker.com) using [Docker Compose](https://docs.docker.com/compose/).

## Installation

Download and extract the latest release
Alternatively, to test the latest changes clone the repository: 
```bash 
git clone https://github.com/jitsi/docker-jitsi-meet && cd docker-jitsi-meet
```
Create a .env file by copying and adjusting env.example
```bash 
cp env.example .env
```
Set strong passwords in the security section options of .env file by running the following bash script
```bash 
./gen-passwords.sh
```
Create required CONFIG directories
```bash 
mkdir -p ~/.jitsi-meet-cfg/{web/letsencrypt,transcripts,prosody/config,prosody/prosody-plugins-custom,jicofo,jvb,jigasi,jibri}
For Windows: echo web/letsencrypt,transcripts,prosody/config,prosody/prosody-plugins-custom,jicofo,jvb,jigasi,jibri | % { mkdir "~/.jitsi-meet-cfg/$_" }
```
Run 
```bash 
docker-compose up -d
```

