# Websocket Server in C 

The code in this repository is supposed to support the awesome websocket 
feature, that was introduced as part of the HTML5 standard. The idea with the
project was originally to learn the C language and furthermore understand the
basics of websockets. 

# Support

The websocket server is written in C and should be supported by the most UNIX 
systems. It does not have any dependencies to other libraries than the standard
libraries in UNIX. As of 09/04-2013 it has been compiled and tested on the 
following operating systems:

* Ubuntu 12.04
* Arch Linux
* MAC OS x 10.8

BEWARE! It does not work in Windows!

# Conventions

As websockets is a pretty new feature, there has been a lot of different 
conventions on how to handle the communication between browser and server. This
websocket server support the following conventions:

* [hixie-75](http://tools.ietf.org/html/draft-hixie-thewebsocketprotocol-75) 
which was supported by Chrome 4 and Safari 5.0.0 and forth.
* [hixie-76](http://tools.ietf.org/html/draft-hixie-thewebsocketprotocol-76)
which was supported by Firefox 4, Chrome 6, Safari 5.0.1 and Opera 11 and forth.
* [hybi-07](http://tools.ietf.org/html/draft-ietf-hybi-thewebsocketprotocol-07)
which was supported by Firefox 6 and forth.
* [hybi-10](http://tools.ietf.org/html/draft-ietf-hybi-thewebsocketprotocol-10)
which was supported by Firefox 7, Chrome 14 and forth.
* [RFC6455](http://tools.ietf.org/html/rfc6455)
which was supported by IE 10, Firefox 11, Chrome 16, Safari 6 and Opera 12.10 
and forth.

The latter RFC6455 is the convention that is supposed to be the standard for
websockets according to the HTML5 standards.

# How to use
With the C code follows a makefile. This is used to compile and run the code.
What you do is simply open your terminal and navigate to the root folder of the
websocket server.

To compile the code, simply type:
`make`

To run the websocket server type:
`make run`

To run the websocket server with valgrind type:
`make valgrind`

The default port of the server is currently port 4567. If you wish to have 
another port you can simply type:
`make run PORT=1111`

When the server is up and running, it has a few commands that could be useful.
These commands can be displayes by typing `help`.

Last but not at least, it is up to the one running the server to decide which 
hosts and origins that is allowed. To choose these addresses, you can edit the 
2 files `Hosts.dat` and `Origins.dat`. The first line in the file indicates the
amount of addresses allowed, and the following lines is the actual addresses 
allowed.

`Hosts.dat` has the information:
<pre>
2
localhost
127.0.0.1
</pre>

`Origins.dat` has the information:
<pre>
2
http://localhost
http://127.0.0.1
</pre>

# Future implementations

In the future, the server should be able to communicate with browsers, 
eventhough the browser is just trying to contact the server using a normal 
HTTP Request. The idea is to implement some kind of COMET server, such that 
the server is useful for old browsers as well.

Another thing that would be preferable is that the server is able to handle
SSL connections. Which includes being able to handle wss:// connections.
