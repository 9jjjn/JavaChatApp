# Chat Application

## Overview

This chat application consists of a server and client implementation in Java. The server handles multiple client connections, allowing users to send and receive messages in real-time. The clients connect to the server and can send messages to other connected clients.

## Features

- **Server**:
  - Listens for incoming client connections on a specified port.
  - Handles multiple clients simultaneously.
  - Broadcasts messages received from one client to all connected clients.
  - Manages client connections and disconnections.

- **Client**:
  - Connects to the server.
  - Sends messages to the server.
  - Receives and displays messages from the server.
  - Prompts the user to enter their name and send messages.

## Requirements

- Java Development Kit (JDK) 22 or higher
- Command-line interface (CLI) for running Java commands

## Getting Started

### 1. Compile the Code

To compile the server and client code, navigate to the directories containing `ChatServer.java` and `ChatClient.java`, respectively, and use the `javac` command:

```bash
javac server/ChatServer.java
javac client/ChatClient.java
2. Run the Server
Open a terminal or command prompt and navigate to the directory where ChatServer.class is located. Run the server with the following command:

```bash
java server.ChatServer
You should see output similar to:

vbnet
Welcome everyone in the chat application!
The server began on port 12345
Waiting for clients to connect...
3. Run Multiple Clients
Open one or more additional terminals or command prompts. Navigate to the directory where ChatClient.class is located in each terminal.

For each client, run:

```bash
java client.ChatClient
Each client will prompt you to enter your name. After entering your name, the client will display the welcome message from the server and will allow you to send messages.

4. Test Communication
## Send Messages:
- Type messages in one client’s terminal and press Enter.
- Verify that the messages appear in all other connected clients’ terminals.

## Check for Duplicate Messages:
- Send the same message multiple times to verify that the server handles duplicate messages correctly.

## Disconnect a Client:
- Close the terminal running one of the clients.
- Verify that the server handles the disconnection properly and that remaining clients continue to operate normally.

##Implementation Details
###Server (ChatServer.java)
- Purpose: Handles client connections and broadcasts messages to all connected clients.
- Key Components:
- ServerSocket: Listens for incoming client connections on a specified port.
- ClientHandler: Handles each client connection in a separate thread.
- clientWriters: A Set that stores PrintWriter objects for each client.
- clientNames: A Map that associates PrintWriter objects with client names.
- Message Broadcasting: Receives messages from one client and sends them to all other clients.

###Client (ChatClient.java)
- Purpose: Connects to the server and allows the user to send and receive messages.
- Key Components:
- Socket: Connects to the server.
- BufferedReader and PrintWriter: Handle input and output streams.
- User Interaction: Prompts the user to enter their name and messages.
- Multithreading: Uses a separate thread to read messages from the server while the main thread handles user input.

Troubleshooting
- No Connection: Ensure the server is running and check that the client is connecting to the correct server address and port.
- No Messages: Verify that messages are being sent and that the server is correctly broadcasting them to all clients.
- Client Disconnection: Ensure proper handling of client disconnections in the server.

License
This project is licensed under the MIT License. See the LICENSE file for details.
