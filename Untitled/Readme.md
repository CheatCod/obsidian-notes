**Lodestone**

Lodestone was originally conceptualized by a team of 3 Minecraft nerds who find the process of self-hosting a Minecraft server tedious and unnecessarily complex. While paid commercial server hosting services exist, they usually take too much control from the user, often have poor performance, and not to mention the costs. So we built one ourselves.

"Anyone should be able to set up their very own server with a few button clicks", that's our end goal for this project.

**Project Structure**

*Note: an "instance" refers to an instance of a Minecraft server* 

Lodestone is broken down into 3 main components:

- **Dashboard** (frontend)
	The dashboard is where the end-user will interact with lodestone, this is where they will manage their instances. This component will be a progressive web app that runs on our server and will be built with react + typescript

- **Client** (backend)
	The client runs on the end user's machine and is responsible for reporting all the necessary information to the frontend through HTTP requests, as well as managing processes (Minecraft servers), managing multiple users with different permissions, and authenticating. This component is built in rust + rocket, with MongoDB being the database.

- **Link** (service)
	Lodestone link is an optional service for lodestone, it allows the user to generate a public IP to their instance instead of port forwarding. It is responsible for authenticating our end users and managing TCP tunnels and subdomains with DNS. Lodestone link will run on our central server and will be built with Firebase, node, typescript, express, and FRP (a tunneling software). 
	*Note: the link's user and authentication system is completely different from the client's user and authentication system*

**Prerequisites**

Nothing, really. I didn't know a thing about any of the technologies mentioned above, had 0 experience with REST APIs and networking.

This project has been an incredible learning experience for me and I hope it will be for you too!

Please check out dev-resources to get started.

**Expectations**

Let's be realistic, you probably won't have the same enthusiasm for this project as I and I don't intend you to. I know you'd rather play league or apex rather than coding up the project, and that is perfectly fine.

If the team is still just the original 3 guys then we wouldn't have any problems, but with each new member comes exponentially more complexity in terms of communication, scheduling, and tasking. The chances are at least one of us will be dependent on a task you are responsible for, and you bailing out on us could cause some serious disruptions.

Thus, we expect you to communicate frequently, set realistic deadlines, and be mindful of your responsibilities.

**Thank you!**

It means the world to us that you are interested in working on this project, and I can't even begin to express my appreciation for the hard hours our team members have put into this project. Thank you!

