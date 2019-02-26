Voting App
=========

A simple distributed application running across multiple Docker containers.

Getting started
---------------
#### Run
```
sudo docker run -d -p 5555:80 --link redis:redis --name vote vote
```