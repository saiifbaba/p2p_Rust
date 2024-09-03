#####
Task is to design a simple p2p gossiping application in Rust. The peer should have a cli interface to start it and connect itself to the other peers. Once connected, the peer should send a random gossip message to all the other peers every N seconds. The messaging period should also be specifiable in the command line. When a peer receives a message from the other peers, it should print it in the console.

# Prerequisites
Rust and Cargo installed. You can install Rust by following the instructions at rust-lang.org.

# Usage
Clone the repository:

git clone <repository-url>
cd p2p-Rust
Build the project:

cargo build --release
Run a peer:

cargo run -- --period=<SECONDS> --port=<PORT> [--connect=<ADDRESS>]
--period <SECONDS> : The period in seconds at which to send random messages.
--port <PORT> : The port number on which the peer listens.
--connect <ADDRESS> (optional): The address of another peer to connect to at startup (e.g., 127.0.0.1:8080).


# Project Structure
src
 |_network
   |_message
   |_mod
   |_peer
-main
-utils
#
.main.rs: The main entry point of the application.
.network/mod.rs: The module for network-related functionality.
.network/message.rs: Contains message-related structs and enums.
.network/peer.rs: Contains peer-related functions such as
handling connections and message passing.
.utils.rs: Contains utility functions for logging and timestamp handling.

# Example
To start a network with three peers:

1. Start the first peer:
cargo run -- --period=5 --port=8080


2. Start the second peer and connect to the first peer:
cargo run -- --period=6 --port=8081 --connect=127.0.0.1:8080

3. Start the third peer and connect to the first peer:
cargo run -- --period=7 --port=8082 --connect=127.0.0.1:8080
