# Server-creation-and-maintenance-using-python

I was recently in the proccess of designing and creating a BaaS server and subsequently searched a lot in order to find the easiest way to create and maintain it while keeping the procedure as simple as possible for someone else to swiftly understand and maintain. Remember that servers do not have a GUI and unless you are really familiar using the terminal you are gonna have a hard time finding what's going on. Which is bad in production scenarios because downtime or slow implementation of features/changes equals to loss of money and user dissatifaction.

This guide is what I wished was out there when I was desperately searching so... LUCKY YOU!

First things first, we will be using python (subsequently you'll have to be a little familiar with the language) and Ubuntu 16 LTS to showcase some "stuff" along the way. Nevertheless, I will try being as abstract as possible in order for you to understand the general concept of "how to" and apply where needed, regardless of operating system, necessities etc... 

The bigger and the more complex a procedure is, the bigger the chances are that something will go wrong because there are more points of failure present. On the other hand when something is as easy as pressing a button or copy-pasting a simple command, what can go wrong, right? Well this is the logic behind a production scenario since, as time passes by in order to stay competent more and more needs emerge subsequently more and more changes are being made and extra features added. System adminstrators and software engineers try to find ways in order for the things they implement, to be bullet-proof and ,at the same time, simple for someone other than them to understand, maintain and modify if need be in the future as fast and as securely as possible.

Lets create 2 hypothetical scenarios. One is that we have a new machine which has to be configured as a backend server by setuping programs, updates, services etc... The second scenario is already having a configured machine that has to be drastically altered to a new state (due to legacy support or incompatibility with new client software).

Those 2 scenarios may be daily routine depending on the nature of a company. Setuping new machines to be part of a cluster or constantly patching an eshop to include new technologies like "samsung pay" or "chat with our experts" are some examples. 

I think it is self explanatory why things like that must be first tested in a simulation environment and then implemented on the production one. But even then, after spending time "trialing and erroring" in the simulation environment the correct procedure, although now known, still has some obscure and uncertain steps that must be tested from the beggining. If something seems to be wrong when said procedure is tested, modifications that will possible solve the problem are made and then... everything again from the beggining! And so on. On top of that, the human factor of implementation adheres to the time being wasted. And we haven't even mentioned the fact that every time a step is altered in the procedure it must be written down (version control). So others after us must know how to, what has been done and how to modify further. The whole thing seems pretty intricate and complicated, right?

Here's where python comes in. There is a way to eliminate the human factor from the procedural scenario by having python do it and at the same time not having to document anything because the python code itself is the documentation. Moreover, testing a whole scenario which may include millions of steps in a simulation environment is actually typing one command and pressing 'enter'. Seriously, no kidding. That's it:

        wget www.webpage-where-you-have-the-file-stored.com/magical-python-file.zip && sudo python magical-python-file.zip

Which means that if the simulation environments are tested at hosting company (like DigitaOcean, Azure or Amazon), which they should, having a freshly installed operating system is a matter of seconds. Copy pasting the command is also a matter of seconds. And since there is no human implementation and python does it all, the procedure that python has to accomplish is a matter of seconds (or hardly ever minutes) too. Unless you're a huge company having servers/clusters with tons of data leading to the procedure taking hours, which you're not because you wouldn't be reading this article. Subsequently testing a feature in simulation is a matter of seconds or minutes in some cases. And it doesn't matter if that procedure is setuping something new or altering something that already exists. The file remains the same! Lets see how and why.

Imagine that among the many steps of a procedure is installing VLC Media Plyer on an ubuntu server. If a human was to do it he would have to open the terminal and type:

        sudo apt-get install vlc
        
Seems pretty easy as a standalone command but what if it was way bigger and among million other commands and had to be executed before a specific file transfer and after a specific security update? Now if we were to do that with a python script the part where the python script executes that command would look like this:
                              
                                // security update
                                
                                vlc_installation = "sudo apt-get install vlc"
                                
                                os.system(vlc_installation)
                                
                                // file transfer
