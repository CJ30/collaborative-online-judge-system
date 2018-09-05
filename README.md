# Collaborative Online Judge System

Collaborative Online Judge System is a single-page web application. The goal is to provide a coding practice platform where users could code and solve problems. 

Provided with algorithm questions, users could choose to solve any questions and also have privilege to contribute new questions to the platform. 

In each problem session, multiple users could edit simultaneously and also send solution to backend where an executor would executes the code and send back the result to users.

I add Nginx server, as load balancer, between multiple code executors and node server (process speed of code executor is slower than request sending speed of node server), to improve system throughput.

## Prerequisites
All softwares are presented in Linux way.
### Install NodeJs:
```
sudo apt-get update
curl -sL https://deb.nodesource.com/setup_8.x | sudo -E bash -
sudo apt-get install -y nodejs
```
### Install Nodemon
```
sudo npm install -g nodemon
```
### Install git
```
sudo apt-get install git
```
### Install angular/cli
```
sudo npm install -g @angular/cli@latest
```
### Install Redis
```
wget http://download.redis.io/releases/redis-3.2.6.tar.gz
tar xzf redis-3.2.6.tar.gz
cd redis-3.2.6
make
sudo make install
cd utils
sudo ./install_server.sh
```
### Install pip3 for python3
```
sudo apt-get update
sudo apt-get -y install python3-pip
sudo pip3 install Flask
```
### Install Docker
```
curl -fsSL https://get.docker.com/ | sh
Setup docker permission:
sudo usermod -aG docker $(whoami)
(you need to logout and login again after set permission)
To start docker when the system boots: sudo systemctl enable docker
```
### Install Nginx
```
(For ubuntu 16.04) Add following two lines into /etc/apt/sources.list
deb http://nginx.org/packages/ubuntu/ xenial nginx
deb-src http://nginx.org/packages/ubuntu/ xenial nginx
Then run:
sudo apt-get update
sudo apt-get install nginx
```

## Getting Started
```
git clone https://github.com/CJ30/collaborative-online-judge-system.git
sh ./launcher.sh
```

## Built with
Here is overall architecture:

![](TODO picture)
* Browser: Angular 2 framework 
* Frontend: NodeJs server + Express router
* WebSocket: Socket io
* Load Balancer: Nginx server
* Executor & Judger: Docker + Flask 
* Cache: Redis
* Database: MongoDB

## Author
* Chengjin Sun (CJ30)


