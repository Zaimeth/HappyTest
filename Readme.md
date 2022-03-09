![Build Status](https://github.com/Zaimeth/HappyTest/actions/workflows/Build.yaml/badge.svg)


# HappyBMI
**This repository was created as one of the stages in ongoing tests**

------------
## Output condition on BMI

| BMI | Status |
| ------ | ------ |
| <=18.5 | Underweight |
| 18.5 - 24.9 | Normal weight |
| 25.0 - 29.9 | Overweight |
| 30.0 - 39.9 | Obese |
| >=40.0 | Morbidly Obese |
------------
## How to use it

### First method

**Using manual method**
- Git Clone this repository
- Open terminal and type "python3 -m venv bmi"
- Open terminal and type "pip install -r requirements.txt"
- Open terminal and type "uvicorn app.main:app --reload"
- Open browser and type "http://127.0.0.1:8000"
- Example to use BMI like this "http://127.0.0.1:8000/api/bmicalculator/?height=1.5&weight=70"

### Second method

**Using Docker**

- Install [docker](https://docs.docker.com/engine/install/) and [docker-compose](https://docs.docker.com/compose/install/) in your local pc
- Run docker-compose

```sh
$ docker-compose build
$ docker-compose up -d
```

- to see the status of the docker running or not, it is by doing the command :
```
$ docker-compose ps
```
- Open browser and type "http://127.0.0.1:8000"
- Example to use BMI like this "http://127.0.0.1:8000/api/bmicalculator/?height=1.5&weight=70"

------------
## API documentation
To view the API Documentation, you can go through the link:
```sh
http://127.0.0.1:8000/docs
```
------------
## CICD
In the CICD process that is used for testing this to this server, we use :
- Github Action 
- Portainer 
- Watchtower 

### Github Action 
Github Action is used as the build process of this service itself, then after the service is built as a docker image, the image will be uploaded to docker hub

### [Portainer](https://www.portainer.io/?hsLang=en) 
Portainer functions as docker management, where we can monitor and view the logs of the services we deploy on the server. I use this because it's suitable for small businesses, but the features themselves are pretty good

### [Watchtower](https://containrrr.dev/watchtower/)

Watchtower is a service where it will check other services that are running to the Docker hub or to other registry containers. It's as simple as pulling the new docker image and then replacing the old docker image. This watchtower-assisted process makes the process of replacing the old docker image with a new one feel very good
