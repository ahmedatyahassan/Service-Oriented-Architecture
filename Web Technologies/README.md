
## Service
The word **“Service”** refers to one person or organization  performing some work or task for another person or organization.

Service term in software industry
 * One application or computer program performing some work for another application or computer program, this work may include some functionality or data sharing.


### Note
* In most cases, application(service) runs in a distributed manner, this means service provider run on one machine and service consumer run on another machine, and connected together by network, but sometimes provider and consumer service run on the same machine.


### Business problems addressed by SOA
* Mergers: this refers to two or more companies or organizations joining to a single.
* Acquisition: this refers to a company increasing its size substantially by buying or acquiring another company. 
* Changing market conditions.
* New technological advances.
* The nature of business relationships.


## RPC → Remote Procedure Call
Is a procedure that makes a call to a remote function look the same as a local function call

![image](https://user-images.githubusercontent.com/64374947/144573324-b4beaa06-d605-452c-bed1-19dc87427568.png)

Online shops can’t directly call the processPayment function on the different nodes, so RPC framework provides what’s called stub function that has the same type signature of the remote function, stub function doesn’t actually process the payment but it does send a message to the service which then does process the payment.

![image](https://user-images.githubusercontent.com/64374947/144573551-c4de4b8c-d22e-4c4c-a72e-1b2214fb713c.png)

The RPC client needs to take args that were passed to that function and translate args into messages that can be sent over the network.

Marshaling args means encoding the args in some way that can be sent over the network such as json, binary, … etc.

The RPC Server translates marshaling  args into args to pass it to the payment Process function or encoding the args in some way that can be sent over the network such as json, binary, … etc.
Based on direction.



RPC has a number of shortcomings that prevent it from being a complete and satisfactory solution for integrating all applications in a large enterprise. We will begin to address some of these shortcomings, including the following: 
There is little room for code reuse because the code for marshalling and unmarshalling and the code for network communication are buried inside the client and server applications
RPC is not language independent
RPC integrates the client and server applications in a point-to-point manner
In RPC the roles of client and server are fixed, and the relationship between the client and the server is not “peer to peer.”

### Note
RPC is not appropriate if a large number of applications need to be integrated.
Think of Point to point being two people talking to each other over the phone. The two can only talk to each other. Peer to peer is like a crowded room or elevator where everyone hears each other's conversations.



## Object request broker 
* It's the most important & core functionality component of CORBA.
* Provide all the communication and marshalling (of arguments and return values) needs of the distributed objects.
* Encapsulating the marshalling code and the networking calls code into a separate software component.
* Separation allowed the same code to be reused by many applications.
* Decoupling between the applications by moving away from point-to-point integration.

The basic working of an ORB is as follows:

![image](https://user-images.githubusercontent.com/64374947/144573844-e0eab2b6-c9f0-4dd1-b410-e69eada4c29b.png)


1. When an object or component wants to use the service of another objector component, it first needs to obtain reference for the object providing service.
2. ORB locates server on behalf of the client
3. ORB ensures that the server is ready to receive the request.
4. ORB on the client side accepts the parameters of the method/function being invoked and marshals the parameters to the network.
5. ORB on the server side unmarshals the parameters and delivers them to the server object.
6. The return value is marshaled and unmarshal at the server side and the client side, respectively, in a similar manner


### Note
* This move away from point-to-point integration may be considered the first step in the evolution of the concept of Enterprise Service Bus (ESB).
* ORBs allow applications running on the same machine and on different machines to communicate. 
