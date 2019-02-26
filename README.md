Voting App
=========

A simple distributed application running across multiple Docker containers.

Getting started
---------------
#### Build Docker Images
```
cd vote/
sudo docker build -t vote-app .
cd ..
cd result/
sudo docker build -t result-app .
cd ..
cd worker/
sudo docker build -t worker-app .
cd ..
```

#### Run Docker Containers
```
sudo docker run -d --name redis redis
sudo docker run -d --name db postgres
sudo docker run -d --name worker-app --link redis:redis --link db:db worker-app
sudo docker run -d -p 7000:80 --link redis:redis --name vote-app vote-app
sudo docker run -d -p 7001:80 --link db:db --name result-app result-app
```