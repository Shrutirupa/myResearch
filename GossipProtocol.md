As the term "Gossip Protocol" suggests, the working of it is based on how an actual gossip around a social circle work. It is also known as Epidemic Protocol based on how an epidemic spreads in an environment. 
So, it is a communication protocol and is used widely in distributed systems.
Understanding the analogy, the protocol spreads a message amongst the nodes within the network as such as a rumour spreads or an epidemic disease spreads. 
This is one of the reason behind this protocol but there are other factors as well which play an important role in answering the "WHY" factor of this protocol such as:
1. Failure Detection
2. Scalability
3. Fault Tolerance
4. Robust
5. Consistency
6. Decentralised
   and many more... 
   
Initially, gossip protocol was proposed to maintain consistency in databases by replicating them at different sites. Then at later stages, gossip protocol is being used for the above factors as well.. 
Let us first understand how gossip protocol disseminates information from one node to another. 
There are 3 states in Gossip Protocol:
1. Susceptible - the node is unaware of the update
2. Infected - The node is aware of the update and hence, spreading it to other nodes
3. Removed - The node knows the update and is not spreading it to other nodes anymore

Based on the above states, there are two models that the protocol follows:
1. SI model (Susceptible - Infected )
2. SIR model (Susceptible - Infected - Removed) 

And these models disseminate an update using any of the following styles:
1. push style - nodes periodically sends(pushes) the recent update(value) to a randomly selected node
2. pull style - nodes periodically ask (pulls) for recent update(value) from a randomly selected node
3. push-pull style - a combination of both

The above styles follow the timestand values for checking if the update received by a node is a new update or out. 

There are two variables that we take into consideration: 
1. Value 
2. Time (more of the timestamp)

Push style:
Suppose, the value is the update that an infected node (say, a) sends to a susceptible node (say, b). 
Under this style, a pushes the value to b i.e send(PUSH, value) -> b 
A timeout is set. 
On receive(PUSH, v), if value.time < v.time, then value <- v

Pull style:
Suppose, the value is the update that an infected node (say, a) sends to a susceptible node (say, b).
Under this style, send(PULL,a,value.time -> b)
On receive(PULL,b,t), if value.time > t, send(REPLY, value) -> b
on receive(REPLY, v), value.time < v.time, then value <- v


Push-Pull style:
Push and Pull are combined together. 


























References:
1. http://nufailm.blogspot.com/2012/02/gossip-protocol-introduction.html
2. http://disi.unitn.it/~montreso/ds/papers/montresor17.pdf
3. http://www.cs.cornell.edu/courses/cs6410/2016fa/slides/19-p2p-gossip.pdf
4. http://highscalability.com/blog/2011/11/14/using-gossip-protocols-for-failure-detection-monitoring-mess.html
5. http://alvaro-videla.com/2015/12/gossip-protocols.html
