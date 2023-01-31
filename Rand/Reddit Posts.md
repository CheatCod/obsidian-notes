# Reddit Posts

## Announcing Lodestone, a self hosted Minecraft server management tool written in Rust & Tauri

Hello r/rust! We’re a team of friends that have been working on Lodestone for around 8 months. We feel like the project is feature-complete enough for a beta release, and we’re hoping to get some feedback! You can check out our project page [here](https://github.com/Lodestone-Team/lodestone). We also have a [Discord](https://discord.gg/PkHXRQXkf6)! Feel free to join and chat around.

Lodestone is an all-in-one self hosted Minecraft server management tool. The backend (we’re tentatively calling it “Lodestone Core”) is written in pure Rust. The frontend dashboard is written in React + TS, and we’re also releasing a desktop client written with Tauri.

The #1 goal of Lodestone is to make self hosting game servers on any platform a streamlined and simple process. We have planned support for other games in the future, including Risk of Rain and Terraria.

Some of the key features we’re launching with are:

- Automatic one-click setup for Minecraft servers (We download Java for you!!)
- Create multiple user accounts with scoped permissions for a collaborative server management experience
- File explorers for each game server
- Virtual consoles for each game server's CLI
- UI to adjust server settings instead of messing around in config files
- Real time notifications on server statuses
- Server monitoring (RAM & CPU usage)
- Full support for Windows, partial support for Linux, with upcoming MacOS support*

We also have some exciting planned features, such as:

- A plugin system that allows you to write automation tasks in JS/TS
- Securely expose your server to the internet without port forwarding
- An event viewer for a granular view of everything in your server logs

This is the biggest Rust project we’ve worked on. It is still in early (but rapid!) development phase, so rough patches are expected. Please give it a try if you are interested. And of course, bug reports/suggestions are welcome!

*Lodestone Core is supported on Windows, and Linux, the dashboard needs more work to adapt to the native web view on Tauri

## Announcing Lodestone, a FOSS self-hosted Minecraft server management tool

Hello r/selfhosted! We’re a team of friends that have been working on Lodestone for around 8 months. We feel like the project is feature-complete enough for a beta release, and we’re hoping to get some feedback! You can check out our project page [here](https://github.com/Lodestone-Team/lodestone). We also have a [Discord](https://discord.gg/PkHXRQXkf6)! Feel free to join and chat around.

Lodestone is an all-in-one self-hosted Minecraft server management tool (some call it "server wrapper" or "server panel"). The backend (we’re calling it “Lodestone Core”) is written in Rust, and the desktop client's frontend is written with React + TS + Tauri. We also have a web app dashboard available.

The #1 goal of Lodestone is to make self hosting game servers on any platform a streamlined and simple process. Lodestone is built with heavily focused on the user experience to minimize the friction of setting up a server. Part of this effort is an intuitive and simple UI we have developed over 4 months.

Here are some of the features currenly implemented
- Automatic one-click setup for Minecraft servers (We manage Java for you!)
- Real time update and notifications on server statuses
- Adjust your server settings in UI instead of messing around in config files
- Create multiple user accounts with scoped permissions for a collaborative server management experience
- File explorers for each game server
- Virtual consoles for each game server's CLI
- Open ports through UPnP 
- Server monitoring (RAM & CPU usage)
- Full support for Windows, partial support for Linux, with upcoming MacOS support*

We also have planned some exciting features, such as:

- A plugin system that can listen and react to server events
- Securely expose your server to the internet without port forwarding
- An event viewer for a granular view of everything in your server logs

This is by far the biggest project we have worked on, and since it is still in its early (but rapid!) development phase, rough patches are expected. Please give it a try if you are interested. And of course, bug reports/suggestions are welcome!