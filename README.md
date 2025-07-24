# ft_irc

> [!IMPORTANT]
> None of my code is publicly available here, but if you're a recruiter, I'd be happy to share it with you upon request.

<p align="center"> 
    <img width="318" height="272" alt="Screenshot from 2025-07-24 13-36-23" src="https://github.com/user-attachments/assets/8735a127-8f64-4862-9796-e45d20ea1649" />
</p>

The ***ft_irc*** project is a network programming and systems design assignment where I built a simplified version of an IRC (Internet Relay Chat) server using C++ and UNIX sockets. The goal was to create a working server that implements key aspects of the IRC protocol — handling multiple clients, parsing commands, and managing channels — all in compliance with RFC standards.
This project introduced me to low-level socket programming, concurrent client handling, text-based protocols, and real-time communication in a distributed environment.

What I had to do:
* Implement an IRC server capable of:
    * Listening for multiple client connections via TCP sockets
    * Handling user authentication with password and nickname
    * Managing channels with user roles (operator, normal user, invited)
    * Parsing and executing core IRC commands:
        * `/join`, `/part`, `/kick`, `/topic`, `/invite`, `/mode`, etc.
* Support key IRC features:
    * Channel creation, joining, and topic updates
    * User-to-user and user-to-channel messages (`PRIVMSG`)
    * Modes like `+i` (invite-only), `+t` (topic lock), and operator privileges
* Handle multiple clients concurrently using non-blocking I/O and `poll()`
* Implement robust error handling, server stability, and protocol compliance

To achieve this, I had to:
* Use UNIX sockets and file descriptors to manage real-time network communication
* Parse raw input line-by-line, tokenize commands and arguments
* Maintain a consistent internal state for all users and channels
* Carefully manage connection lifecycles: connect, authenticate, disconnect
* Implement clean signal handling (`SIGINT`, etc.) for graceful shutdown

Bonus Part: IRC Bot with Moderation Features and Fun Commands
* For the bonus, we developed a simple but interactive IRC bot that connects as a client and listens/responds to user input within a channel.
* What the bot could do:
    * Respond to fun, useless commands (e.g., `!ping`, `!flip`, `!help`, etc..)
    * Moderate the channel with commands like:
        * `!mute <nickname>` → prevents a user from sending messages
        * `!unmute <nickname>` → restores speaking privileges
        * `!ban <nickname>` → kicks and blocks a user from rejoining
        * `!unban <nickname>` → lifts the ban
    * Detect specific keywords or patterns and respond automatically

What I Learned:
* Writing a client-side bot that communicates via the IRC protocol
* Building a modular command handler for custom bot commands
* Managing mute/ban state internally and enforcing it within the server logic
* Simulating real IRC moderation features (via protocol commands or extensions)
* Understanding the complexity of even basic automation in a real-time chat system

What I Learned:
* Core principles of network programming using sockets in C++
* How to manage asynchronous I/O with multiple clients via `poll()`
* Parsing and implementing a text-based protocol from scratch
* Maintaining internal state and enforcing protocol-level rules
* Building and extending a modular server with clean command processing
* Writing a bot that interacts with a live protocol, handles chat logic, and simulates moderation

ft_irc was a technically rich and challenging project that pushed my understanding of low-level networking, protocol design, and concurrent client-server architecture. Building a custom IRC server from scratch — and extending it with a working bot that moderates and interacts with users — gave me a strong foundation in real-time systems programming and showed how even old protocols remain complex and powerful under the hood.
This project was a deep dive into system-level development, and the bot bonus made it feel like a complete mini-platform — dynamic, interactive, and fully under control.

Project done with [heperez](https://github.com/hdprz) and [bepoisoo](https://github.com/bepoisso)
