# Server-creation-and-maintenance-using-python

I was recently in the proccess of designing and creating a BaaS server and subsequently searched a lot in order to find the easiest way to create and maintain it while keeping the procedure as simple as possible for someone else to swiftly understand and maintain. Remember that servers do not have a GUI and unless you are really familiar using the terminal you are gonna have a hard time finding what's going on. Which is bad in production scenarios because downtime or slow implementation of features/changes equals to loss of money and user dissatifaction.

This guide is what I wished was out there when I was desperately searching so... LUCKY YOU!

First things first, we will be using python (subsequently you'll have to be a little familiar with the language) and Ubuntu 16 LTS to showcase some "stuff" along the way. Nevertheless, I will try being as abstract as possible in order for you to understand the general concept of "how to" and apply where needed, regardless of operating system, necessities etc... 

The bigger and the more complex a procedure is, the bigger the chances are that something will go wrong because there are more points of failure present. On the other hand when something is as easy as pressing a button or copy-pasting a simple command, what can go wrong, right? Well this is the logic behind a production scenario since, as time passes by in order to stay competent more and more needs emerge subsequently more and more changes and being made and extra features added. System adminstrators and software engineers try to find ways in order for the things they implement, to be bullet-proof and ,at the same time, simple for someone other than them to understand, maintain and modify if need be in the future as fast and as securely as possible. Because remember. Downtime is bad. 
