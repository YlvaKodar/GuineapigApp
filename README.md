# 🐹 A Guineapig console game app repo for containerization experimentation
 
This repo is for trying out containerization with docker init.
The app it self is a simple console game I made as an exercise when I started to learn Java.
 
## Features
 
- A very short, basic and railroaded console game
- Guineapig superheroes
 
## Requirements 
To containerize it you need:
 
- Docker Desktop v. 4.19 or later.
- Git CLI.
 
## Clone the repository

```bash
git clone https://github.com/YlvaKodar/GuineapigApp.git
```

## Containerize
 
```bash
cd GuineapigApp
docker init
```
 
When prompted:
- Platform: **Java**
- Relative directory: **./src**
- Java version: **21**
- Port: **9000** (not actually used, but Docker needs you to make a hypothetical choice)

## Build and run without compose

From inside the the repository, run the docker build and docker run commands. Make sure to include the -t and -it flags to ensure the terminal staying open and interactive.

```bash
docker build -t guineapigs .
docker run -it guineapigs
```

## Build and run with compose

Open up your `compose.yaml` and add these two lines under `ports`. (This will ensure the terminal staying interactive.)
 
```yaml
stdin_open: true
tty: true
```
 
From inside the the repository, run the docker compose command.
 
```bash
docker compose run server
```
 
## Project structure
 
```
GuineapigApp/
├── pom.xml
├── mvnw
├── mvnw.cmd
├── .mvn/
└── src/
    └── main/
        └── java/
            ├── Guineapig.java
            ├── GuineaChallenge.java
            └── StartGuineaGame.java
```
 
