# RTS Cloudstepping

## Project Proposal
[CSC466 Project Proposal.pdf](https://github.com/SirDuck145/CCS-research-project/files/10211653/CSC466.Project.Proposal.1.pdf)


## Project Midway Update
I initially started out by planning a concept for my design using the ideas of “super peers” in the cloud to connect multiple players to a single node. Then having those nodes synchronize with other “super” peers. The hope was to create an environment that could host a 100 player battle royale RTS game like starcraft or Age of Empires. However a few key issues arose as I tried to develop this idea further.

First, RTS games are handled through a concept called lockstepping. This is a technique to bind commands from the user to a specific “turn” on the server. This ensures that all players actions are rendered at the same turn with the same amount of delay.Then all clients render their own simulation. In the extreme case, If a player's delay is too high their command will be added to a later turn.

This leads to a few issues that I faced. The first being that a single device would need to run the logic and render the entire gamespace for up to 100 clients. Ideally, this could lead to around 500 units per client and with 100 clients. This would be 50 thousand units to render and handle logic for. While I don’t know the exact feasibility of this, it seemed unlikely to me. The second issue I ran into was that the open source RTS game I was planning on converting for my research was going to require significantly more work than I had intended for it. The project was incredibly old and would require a lot of changes just to get it functioning again.

These two factors along with the advice to simplify our project ideas caused me to make a shift.

I started looking at cloud gaming as a potential avenue to focus down. I found a few interesting articles namely An Introduction to Online Video Game QoS and QoE Influencing Factors written in 2018 as a launching point and A hybrid graphics/video rate control method based on graphical assets for cloud gaming published August 2021. The latter article talks about using the player's device to offset some of the cost of streaming the game to help improve the player experience.

Most of these articles are based around the concept and idea for a user to have a thin client. However what I am more interested in, is the unique ability for a cloud service to have incredible processing power. My idea is to couple this processing power with a relatively “robust” client. My current idea is to have a multiplayer game hosted in the cloud. The server would simulate the game state and also synchronize the players actions. This server would then report back the game state to the clients. The client then renders the difference between the newly received state and their previous one.

While this is not the most widely applicable model my interest still lies in a large number of players changing and accessing a data set together.

As for work that I have actually done on this idea since the change, I started creating a program to simulate a client and server connection. My goal is to create a simulation for the number of dropped frames based on bandwidth, delay, and rendering power of the client device.


## Project Demo and Presentation
[![Link to my project video](https://img.youtube.com/vi/n_HEaKjvIE4/0.jpg)](https://www.youtube.com/watch?v=n_HEaKjvIE4)

## Project Report
ABSTRACT   
Real Time Strategy (RTS) games haven’t had a ton of networking innovation since the creation of lockstepping. For the most part lockstepped RTS games haven’t required new networking strategies. This is still true today. However with the recent blow up of the battle royale genre, it left me thinking a massive player count RTS game would be really neat. There has never been a massively multiplayer RTS game such as starcraft or company of heroes. (At least that I am aware of.) While this may be in part due to design challenges, another important factor is the scalability of a lockstepped system. RTS games require hundreds to thousands of units for each player. You can imagine how adding a new player then leads to syncing massive amounts of information across players devices. For this paper it has two key points of focus. The first is my newly proposed state based streaming via a cloud gaming solution. The second topic of focus is the application of my state based streaming cloud gaming solution to the RTS genre which I have called cloudstepping.   

FULL REPORT   
[RTS CloudStepping.pdf](https://github.com/SirDuck145/CCS-research-project/files/10211609/RTS.CloudStepping.pdf)
