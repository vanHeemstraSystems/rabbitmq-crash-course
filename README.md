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


Source Code: https://github.com/hnasr/javascript_p...

Docker commands here 
https://github.com/hnasr/javascript_p...

Example

Schedule async job

￼

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


https://www.squaremobius.net/amqp.nod...

https://www.rabbitmq.com/tutorials/tu...


🏭 Software Architecture Videos
https://www.youtube.com/playlist?list...

💾 Database Engineering Videos
https://www.youtube.com/playlist?list...

🛰 Network Engineering Videos
https://www.youtube.com/playlist?list...

🏰 Load Balancing and Proxies Videos
https://www.youtube.com/playlist?list...

🐘 Postgres Videos 
https://www.youtube.com/playlist?list...

🧮 Programming Pattern Videos 
https://www.youtube.com/playlist?list...

🛡 Web Security Videos
https://www.youtube.com/playlist?list...

🦠 HTTP Videos
https://www.youtube.com/playlist?list...


🐍 Python Videos
https://www.youtube.com/playlist?list...

🔆 Javascript Videos 
https://www.youtube.com/playlist?list...


Support me on PayPal  https://bit.ly/33ENps4 
Become A Patron https://www.patreon.com/join/hnasr?

Stay Awesome!
Hussein
