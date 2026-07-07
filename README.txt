🎫 Event Ticketing Smart Contract

A decentralized Event Ticketing System built with Solidity that allows organizers to create events, users to purchase tickets using ETH, and securely transfer tickets to other users.

🚀 Features
🎉 Create an event
🎟 Buy event tickets using Ether
🔄 Transfer tickets to another wallet
📅 Prevent ticket purchases after the event date
💰 Automatic payment verification
📊 Track remaining tickets
🔐 Store all event information on-chain
🛠 Tech Stack
Solidity ^0.8.x
Remix IDE
Ethereum Virtual Machine (EVM)
📂 Smart Contract Functions
1. createEvent()

Creates a new event.

Parameters

Parameter	Type	Description
name	string	Event name
date	uint	Future UNIX timestamp
price	uint	Ticket price in Wei
ticketCount	uint	Total tickets available

Example:

createEvent(
    "Web3 Seminar",
    1800000000,
    1000000000000000,
    50
);
2. buyTicket()

Allows users to purchase one or more tickets.

Parameters

Parameter	Type
id	uint
quantity	uint

Requirements

Event must exist
Event date must be in the future
Correct ETH amount must be sent
Enough tickets must be available

Example

buyTicket(0,2);

with

Value = ticketPrice × quantity
3. transferTicket()

Transfers purchased tickets to another wallet.

Parameters

Parameter	Type
id	uint
quantity	uint
to	address

Requirements

Event exists
Event hasn't occurred
Sender owns enough tickets

Example

transferTicket(
    0,
    1,
    0xReceiverAddress
);
📦 Data Structures
Event Struct
struct Event {
    address organizer;
    string name;
    uint date;
    uint price;
    uint ticketCount;
    uint ticketRemain;
}
Mappings
mapping(uint => Event) public events;

mapping(address => mapping(uint => uint))
public tickets;
🔄 Workflow
Organizer
     │
     ▼
Create Event
     │
     ▼
Users Buy Tickets
     │
     ▼
ETH Sent to Smart Contract
     │
     ▼
Remaining Tickets Updated
     │
     ▼
Users Can Transfer Tickets
🧪 Testing

You can test this contract using Remix IDE.

Deploy

Deploy the contract.

Create Event
Name: Web3 Seminar

Date: Future UNIX Timestamp

Price: 1000000000000000 (0.001 ETH)

Ticket Count: 50
Buy Ticket
Event ID: 0

Quantity: 2

Value: 2000000000000000 Wei
Transfer Ticket
Event ID: 0

Quantity: 1

Receiver Address: 0x...
📚 Solidity Concepts Used
Structs
Mappings
Nested Mappings
Payable Functions
msg.sender
msg.value
require()
Storage vs Memory
block.timestamp
Ether Transactions
🚧 Future Improvements
Frontend with React.js
Connect using Ethers.js
MetaMask Integration
Hardhat Development Environment
Event Cancellation
Refund System
Event Images & Metadata
NFT-based Tickets (ERC-721)
Event Search & Filtering
Owner Withdraw Function
Unit Tests
Deploy to Sepolia Testnet

!<img width="277" height="206" alt="Image" src="https://github.com/user-attachments/assets/246db7d5-326e-4f25-b433-7429d307819b" />

!<img width="277" height="206" alt="Image" src="https://github.com/user-attachments/assets/23646ae0-1565-4cc2-934e-11a89cce9e86" />


!<img width="330" height="486" alt="Image" src="https://github.com/user-attachments/assets/3122e7ac-0f38-4245-a0f3-32ebbd75794b" />

!<img width="316" height="432" alt="Image" src="https://github.com/user-attachments/assets/01e3802b-0992-420c-8b00-8d4b256cd996" />

!<img width="316" height="432" alt="Image" src="https://github.com/user-attachments/assets/11ed41f8-4a0a-4a71-9588-df8535d384cf" />

This project is licensed under the GPL-3.0 License.

👨‍💻 Author

Amrit Marasini

💼 Blockchain Developer (Learning)
🌐 Passionate about Web3, Smart Contracts, AI, and Full-Stack Development

⭐ If you found this project useful, consider giving it a Star on GitHub!
