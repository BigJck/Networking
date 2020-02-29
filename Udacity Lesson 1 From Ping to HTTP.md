## Lesson 1 From Ping to HTTP



#### Ping: received by Operation system, without a ping server

#### HTTP: received by web server

ex:	 printf 'HEAD / HTTP/1.1\r\nHost: en.wikipedia.org\r\n\r\n' | nc en.wikipedia.org 80

​	first web: what web site we want

​	second web: what host should nc connect to?

​	| : means pip to 

​	nc: net cat, sending string over network  try: 'man cat'  

#### NC: read 'man nc'

​	listen on a port:  nc -l 3456

​	use 'nc -l 3456' and 'nc localhost 3456' to communicate with each other

#### Port Number:  Os distinguish different traffic by looking at address and port number

​	[1,65535] but [1, 1024] needs ROOT or Sudo

​	normally only one program could  listen to one port at the same time

​	use 'sudo lsof -i' to see network sockets

#### Communication between nc and browser

 1. nc -l 3456; browser: ip:port 

    nc got http request and header all browser sent 

 2. printf 'HTTP/1.1 302 Moved\r\nLocation: https://www.eff.org/' | nc -l 2345; browser: ip:port

    browser would display https://www.eff.org, nc will print http request and exit



#### *net cat is only a simple way to show internet, there are different way for server to handle multiple connection at once like pool of threads, or quickly switch between handling requests

