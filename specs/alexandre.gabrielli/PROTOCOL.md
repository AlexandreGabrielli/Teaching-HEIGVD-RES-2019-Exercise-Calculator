# Spécifications

* What transport protocol do we use?

  TCP

* How does the client find the server (addresses and ports)?

  Address: we will use only localhost you need to Run the Multithreads application

  Port: 1212

* Who speaks first?

  The Server cause he say the version and say how to ask help 

* What is the sequence of messages exchanged by the client and the server?

  ```sequence
  Server->client : version 1.0 type help for help
  client->Server : help
  Server->client : <List of commande implemente>
  client->Server : man add
  Server->client : <man page for add>
  Client->Server : add 5 3
  Server->client : 8
  
  ```

* What happens when a message is received from the other party?

 if you're Server: parse the Input with space and return the result of command ask (see message)
 
 If you're Client : print the output command

* What is the syntax of the messages? How we generate and parse them?
```
   message ::= <op> <var1> <var2>
  <op>::= add | div | sub | mult 
  <var2>::= <number>
  <var1>::= <number>
  <number>::= [0 | 1 | 2 | 3 |4 | 5 | 6 | 7 | 8 | 9]
```  
  
* Who closes the connection and when?

  * The client in general case
  * The server in case of a Timeout
  * The server if an error occurred
