📡 LAN File Transfer Using Sliding Window Protocol

A networking project that implements reliable file transfer over a Local Area Network (LAN) using the Sliding Window Protocol, simulating core behaviors of TCP such as flow control, acknowledgements, retransmissions, and packet sequencing.

📌 Project Overview

This project demonstrates how reliable data transfer works at the transport layer by implementing the Sliding Window Protocol from scratch.

The system works in a client–server model, where:

The client reads a file and breaks it into packets.

Packets are sent over the network using a sliding window mechanism.

The server receives packets, sends acknowledgements (ACKs), and reassembles the file in correct order.

Lost or corrupted packets are detected and retransmitted.

The project is designed for LAN environments to provide fast and efficient file transfer while ensuring data integrity and reliability.

🎯 Key Objectives

To understand and implement flow control

To simulate reliable data transmission

To demonstrate packet loss handling

To understand network congestion handling concepts

To visualize transport layer protocol operations

🧰 Technologies Used
Programming Language

C / C++ (Socket Programming)

Networking Concepts

Sliding Window Protocol

TCP-like Reliability Mechanisms

Sequence Numbers

Acknowledgements (ACKs)

Timeout & Retransmission

Flow Control

Tools

GCC Compiler

Linux / Windows (WSL or MinGW)

Wireshark (optional for packet analysis)

⚙️ How the System Works (Workflow)

Client selects a file to send.

File is divided into multiple fixed-size packets.

A sliding window of size N is used:

Sender can send up to N packets without waiting for ACKs.

Receiver:

Sends positive ACKs for correctly received packets.

Requests retransmission if a packet is lost.

Sender:

Slides the window forward when ACKs are received.

Retransmits packets when timeout occurs.

Server rebuilds the file in the correct order.

📂 Project Structure
LAN-File-Transfer-Sliding-Window/
│
├── client.c
├── server.c
├── sliding_window.c
├── sliding_window.h
├── Makefile
├── README.md
└── test_files/

🚀 How to Run the Project
1️⃣ Compile the Code
gcc server.c -o server
gcc client.c -o client

2️⃣ Start the Server
./server


The server starts listening on a specific port.

3️⃣ Run the Client
./client


Enter:

Server IP Address

Port Number

File name to transfer

🧪 Example Output

Client Side:

Sending packet 1
Sending packet 2
Sending packet 3
ACK received for packet 1
Sliding window updated


Server Side:

Packet 1 received
Packet 2 received
ACK sent
File reconstruction in progress...

✅ Functionalities
Sender (Client)

File selection and reading

Packet creation and sequencing

Sliding window transmission

Timeout-based retransmissions

Receiver (Server)

Packet validation

Out-of-order packet handling

ACK generation

File reconstruction

🔐 Reliability Features Implemented
Feature	Description
Sliding Window	Controls number of unacknowledged packets
Sequence Numbers	Maintains packet ordering
Timeout	Detects packet loss
Retransmission	Resends lost packets
ACK System	Confirms delivery
📈 Performance Benefits

Reduces waiting time compared to Stop-and-Wait

Improves network utilization

Efficient for large file transfers on LAN

📚 Applications

LAN File Sharing Systems

Reliable Data Transfer Simulations

Networking Protocol Teaching Tool

OSI/TCP-IP educational projects

🚧 Future Enhancements

Add Selective Repeat ARQ support

Add encryption for data packets

GUI-based client interface

Progress bar for file transfer
