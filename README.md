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

See also: https://docs.docker.com/engine/reference/run/

OPTIONAL: The --rm flag is there to tell the Docker Daemon to clean up the container and remove the file system after the container exits. This helps you save disk space after running short-lived containers.

OPTIONAL: The -it flag tells docker that it should open an interactive container instance.

OPTIONAL: A useful parameter to pass to docker run is the -d flag. This flag causes Docker to start the container in “detached” mode. A simple way to think of this is to think of -d as running the container in “the background,” just like any other Unix process.

OPTIONAL (default = localhost): Name your container's hostname (-hostname): rabbitmq-server

REQUIRED: Name your container (-name): rabbitmq

OPTIONAL: Set the external port (-p) to the RabbitMQ Web UI Management Console: 15672 (you can choose some other number as well)

OPTIONAL: Set the internal port (:) to the RabbitMQ Web UI Management Console: 15672 (default port for RabbitMQ Server)

REQUIRED: Set the external port (-p) to the RabbitMQ Server Client connection: 5672 (you can choose some other number as well)

REQUIRED: Set the internal port (:) to the RabbitMQ Server Client connection: 5672 (default port for RabbitMQ Server)

REQUIRED: Mention the Image from which to pull the RabbitMQ docker: rabbitmq or rabbitmq:3-management (which includes the Web UI Management Console)

```
$ docker run --rm -it -d --hostname rabbitmq-server --name rabbitmq -p 15672:15672 -p 5672:5672 rabbitmq:3-management

```

If not run in "detached" mode, leave this container to run, switch to another terminal to prevent stopping the container.

# RabbitMQ Web UI management Console

If you started docker with rabbit:3-management the Web UI Management Console can be seen in your local browser at (**note**: depends on the port you've set, here default):

http://localhost:15672

Login before password change is:

Username: guest

Password: guest

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

# Write your first Publisher code

Create a new file called "publisher.js" in the root of your project, and add the following code to it:

```

```

After having done so, make sure you install amqplib as is required by running the following command (it will add it to package.json for future reuse):

```
npm install ampqlib --save
```

# Debug your first Publisher code

See also https://code.visualstudio.com/docs/nodejs/nodejs-debugging
and https://code.visualstudio.com/docs/introvideos/debugging

Select the publisher.js file and set a breakpoint inside the try section

Next, choose "" from the top menu of Visual Studio Code and select the following Environment (if not done so already before):

- Node.js

Your code will run and it will bring you to the breakpoint.

You will see the following output in the console:

```
Job sent successfully 19
```

***NOTE***: Kill the connection to the queue by stopping the debugger.

# Check for New Messages in the Web UI Management Console

Check the Web UI Management Console for new messages.

http://localhost:15672/#/queues/

You should see a new message in the queue named "jobs".

# Create your first Consumer code

