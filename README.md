# Secure-Chat-Room-with-SSL-TLS-Encryption

## Overview
This project implements a secure, multi-client chat room using Python's socket and ssl libraries. The server and clients communicate over an encrypted SSL/TLS connection, ensuring that messages are transmitted securely. This setup is ideal for learning about basic socket programming, threading, and secure communication using SSL/TLS in Python.

## Features
SSL/TLS Encryption: All communications between clients and the server are encrypted, providing privacy and security.
Multi-Client Support: The server can handle multiple clients simultaneously, allowing multiple users to chat in the same room.
Alias System: Users can choose an alias when they join the chat, which is displayed with their messages.

## Project Structure
client.py: The client-side script that connects to the server, sends and receives messages over a secure connection.

server.py: The server-side script that accepts client connections, broadcasts messages to all connected clients, and handles client disconnections.
cert.pem & key.pem: SSL/TLS certificate and private key files used by the server to encrypt communications.

## Getting Started
### Prerequisites
Python 3.x: Ensure that Python is installed on your system.
OpenSSL: Used to generate the SSL/TLS certificates.

### Generating SSL/TLS Certificates
To create a self-signed SSL/TLS certificate, you can use OpenSSL:  
openssl req -newkey rsa:2048 -nodes -keyout key.pem -x509 -days 365 -out cert.pem  
This will generate cert.pem and key.pem, which are required by the server.

### Running the Server
Start the server by running:  
python3 server.py  
The server will start listening for incoming client connections.
Running the Client  
On a different terminal or machine, run the client script:  
python3 client.py  
Enter an alias when prompted. You can then start sending and receiving messages.
How It Works
Server: The server initializes with SSL/TLS support using ssl.create_default_context. It listens for incoming connections and handles each client in a separate thread.
Client: Each client connects to the server using a secure socket. Messages are exchanged securely using SSL/TLS encryption.
### Example Usage
Run the server:  
python3 server.py
Run multiple clients:  
python3 client.py  
Each client can chat with others securely in the chat room.
