rabbitmq-crash-course
# RabbitMQ - Crash Course

Based on "RabbitMQ Crash Course" at https://www.youtube.com/watch?v=Cie5v59mrTg

RabbitMQ

RabbitMQ is an open source distributed message queue written in Erlang and supports many communication protocols.  It was trying to solve the spaghetti 🍝 mesh architecture where every client is communicating with other client in System  by introducing an extra layer in the middle. 

(slide) 

In this video we will explain basic components of RabbitMQ Such as AMQP, channel, queue, publisher, consumer and some stuff, we will also learn how to spin up a RabbitMQ server and we will finally write some code to develop a publisher client that post messages to RabbitMQ. We will also write the consumer piece which will be the code that reads rabbitMQ. Finally I will talk about my personal thoughts on this tech. 

- RabbitMQ Components(slide) 
- *Publisher
- *Consumer
- *Connection
- *Channel
- *Queue
- Spin RabbitMQ server with Docker
- Write a Publisher client NodeJs
- Write a Consumer client Nodejs
- My Thoughts about this tech
- Summary


timecodes

0:00 Intro

2:00 RabbitMQ Components

8:30 Spin up RabbitMQ Docker Container

11:00 Write a Publisher client NodeJs

20:30 Write a consumer client NodeJs

33:50 My thoughts on RabbitMQ 

Source Code: https://github.com/hnasr/javascript_playground/tree/master/rabbitmq

Docker commands here 
https://github.com/hnasr/javascript_playground/blob/master/rabbitmq/scripts.md

Example

Schedule async job

Exchange 
Queues
Publisher
Consumer
AMQP
Channel
Connection 


HTTP 
AMQP
Uses Channels and Queues
Multiples channels into one connections


https://www.squaremobius.net/amqp.node/channel_api.html#channel_bindExchange

https://www.rabbitmq.com/tutorials/tutorial-three-javascript.html


🏭 Software Architecture Videos
https://www.youtube.com/playlist?list=PLQnljOFTspQXNP6mQchJVP3S-3oKGEuw9

💾 Database Engineering Videos
https://www.youtube.com/playlist?list=PLQnljOFTspQXjD0HOzN7P2tgzu7scWpl2

🛰 Network Engineering Videos
https://www.youtube.com/playlist?list=PLQnljOFTspQUBSgBXilKhRMJ1ACqr7pTr

🏰 Load Balancing and Proxies Videos
https://www.youtube.com/playlist?list=PLQnljOFTspQVMeBmWI2AhxULWEeo7AaMC

🐘 Postgres Videos 
https://www.youtube.com/playlist?list=PLQnljOFTspQWGrOqslniFlRcwxyY94cjj

🧮 Programming Pattern Videos 
https://www.youtube.com/playlist?list=PLQnljOFTspQV1emqxKbcP5esAf4zpqWpe

🛡 Web Security Videos
https://www.youtube.com/playlist?list=PLQnljOFTspQU3YDMRSMvzflh_qXoz9zfv

🦠 HTTP Videos
https://www.youtube.com/playlist?list=PLQnljOFTspQU6zO0drAYHFtkkyfNJw1IO


🐍 Python Videos
https://www.youtube.com/playlist?list=PLQnljOFTspQU_M83ARz8mDdr4LThzkBKX

🔆 Javascript Videos 
https://www.youtube.com/playlist?list=PLQnljOFTspQWab0g3W6ZaDM6_Buh20EWM


Support me on PayPal  https://bit.ly/33ENps4 
Become A Patron https://www.patreon.com/join/hnasr?

Stay Awesome!
Hussein

# Spin up a Linux Server

We use a Linux Server on paperspace.com: 'RabbitMQ' (Ubuntu)

# Check Docker Installation

In the terminal type the following to check if Docker is installed:

```
$ sudo docker run hello-world
```

You will be prompted as follows if Docker is installed:

```
$ ...
$ Hello from Docker!
$ ...
```

# Install Docker container with RabbitMQ

Name your container (-name): rabbitmq
Set the external port (-p) to the RabbitMQ Server: 5672 (you can choose some other number as well)
Set the internal port (:) to the RabbitMQ Server: 5672 (default port for RabbitMQ Server)
Mention the Image from which to pull the RabbitMQ docker: rabbitmq

```
$ docker run --name rabbitmq -p 5672:5672 rabbitmq

```

Leave this container to run, switch to another terminal to prevent stopping the container.

# Install Visual Studio Code

To create and modify the Publisher(s) and subscriber(s), we use Visual Studio Code which can be installed for free from https://code.visualstudio.com/

See https://code.visualstudio.com/docs/setup/linux

Download the Debian distribution from https://go.microsoft.com/fwlink/?LinkID=760868

Install the downloaded file (replace < file > with the actual file name of the download, e.g. code_xxx):

```
sudo apt install ./<file>.deb
```

Installing the .deb package will automatically install the apt repository and signing key to enable auto-updating using the system's package manager.

The repository and key can also be installed manually with the following script:

```
wget -qO- https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > packages.microsoft.gpg
sudo install -o root -g root -m 644 packages.microsoft.gpg /etc/apt/trusted.gpg.d/
sudo sh -c 'echo "deb [arch=amd64 signed-by=/etc/apt/trusted.gpg.d/packages.microsoft.gpg] https://packages.microsoft.com/repos/vscode stable main" > /etc/apt/sources.list.d/vscode.list'
```

Then update the package cache and install the package using:

```
sudo apt-get install apt-transport-https
sudo apt-get update
sudo apt-get install code # or code-insiders
```

# Start Visual Studio Code

After installation you can start Visual Studio Code from the terminal as follows:

```
$ code
```

# install NodeJS and NPM

... instructions to follow soon, see https://www.geeksforgeeks.org/installation-of-node-js-on-linux/

Run the following command from your terminal:

```
sudo apt install nodejs
```

Run the following command from your terminal:

```
sudo apt install npm
```

# Initiate your repository in Visual Studio Code

Inside your project (rabbitmq-crash-course) in Visual Studio Code, run the following command from a Terminal:

```
npm init -y
```

Set your Git credentials:

```
$ git config --global user.email "wvanheemstra@icloud.com"
$ git config --global user.name "Willem van Heemstra"
```

Run the following command from your terminal:

```
sudo apt install nodejs
```
