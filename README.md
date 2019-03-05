# How to Dockerize a React App and Deploy in Elastic Beanstalk

<img src="https://github.com/ryanlb777/Docker-Demo/blob/master/react_eb.PNG"/>


### Docker Configuartion Steps

__1. Create file called "Dockerfile" and add the following lines, be sure to change version to a number i.e: 10.12.0
Use node -v to find version__

```
FROM node:version
container .

WORKDIR /app

COPY . /app

RUN npm install

CMD npm start

EXPOSE 3000
```

__2. Create .dockerignore file and add in the following lines__

```sh

node_modules
npm-debug.log

```


### Docker Build Steps

__1. Build docker first__

```sh
docker build -t docker-name .
```
__2. Run docker to test.__

```sh
docker run -p 8081:3000 professional-portfolio
```

### Elastic Beanstalk Steps

__1. Commit changes to git__
```sh


git add .

git commit -m "Eb Deploy Settings"

git push
```

__2. Initialize EB__
```sh

eb init 

Select default -> Create new application -> Enter application name -> Setup ssh
```
__3. Create EB Environment__
```sh

eb create

Select default -> Select Name
```
__4. Deploy EB__
```sh

eb use environment name

eb deploy
```
__5. Confirm EB is deployed__
```sh

eb open

```


### Author: 
1. Ryan LeBon
2. AWS & Docker
