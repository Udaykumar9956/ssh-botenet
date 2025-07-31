🧠 Botnet Control Panel
A Python-based SSH botnet command-and-control system, designed for educational and authorized penetration testing purposes only. This tool allows you to connect to multiple SSH-enabled machines (bots) and execute commands, interact via bash, or launch simulated DDoS attacks on a test server.

⚠️ Legal Disclaimer
This project is intended strictly for educational purposes and authorized network testing only.
Do NOT use this tool on any system or network without explicit permission from the owner.
Unauthorized use may violate computer crime laws and can result in severe consequences.

🛠️ Features
✅ SSH-based botnet communication using pxssh
✅ Persistent botnet session saving & reloading (botnet.json)
✅ Bash shell & remote command execution
✅ Simulated DDoS attack types:
SYN Flood
UDP Flood
ICMP Flood
TCP Connect Flood
HTTP GET Flood
Multi-vector attack (SYN + UDP + ICMP)
📁 Project Structure
├── botnet.py           # Main control panel for managing bots
├── server.py           # Dummy target server to test DDoS modules
├── botnet.json         # Auto-generated file storing bot details
└── README.md           # Documentation
🧩 Dependencies
Library	Purpose
scapy	For packet crafting (used in DDoS module)
pexpect	To handle SSH interaction via pxssh
colorama	For colorful terminal outputs
🚀 Usage
1. Start the Dummy Test Server (on your target machine)
python server.py
🛠️ Note: The default port is 8080. You can change it inside the script if needed.

2. Launch the Botnet Control Panel (on your Kali Linux machine)
sudo python3 botnet.py
⚠️ sudo is required for packet crafting with Scapy.

📋 Menu Options (Detailed)
1. List Bots
Displays all currently connected bots in the botnet.

Shows:

IP address
Port
Username
Connection status (Connected / Disconnected)
2. Run Command
Broadcasts a single command to all connected bots.

The command is executed remotely on each bot.

Useful for:

Checking uptime
Fetching OS info
Running updates, etc.
Example: 
$ Enter a command to run: uname -a
3. Bash
Enters an interactive bash-like mode.

Type commands one-by-one; each is sent to all bots.

Type exit to return to the main menu.

Example:
bash>>> whoami
bash>>> ls /home
4. Add Bot
Adds a new SSH-based bot to the control panel.

You will be prompted to enter:

IP address
Port (default: 22)
Username
Password
The tool will attempt to establish an SSH session via pxssh.

✅ On success, the bot is saved to botnet.json.

5. DDOS
🚨 For testing purposes only.
Use only on authorized systems like the included server.py.

Launches various packet-based DDoS attacks using Scapy and raw sockets.

Attack Types Available:

SYN Flood – Spoofed TCP SYN packets
UDP Flood – High-volume UDP datagrams
ICMP Flood – Ping flood (ICMP Echo Requests)
TCP Connect Flood – Opens/closes connections rapidly (no root required)
HTTP GET Flood – Raw HTTP GET requests
Multi-vector – Combines SYN + UDP + ICMP attacks
You'll be prompted to:

Enter target IP and port
Choose attack type
Specify number of packets/requests
6. Exit
Saves the current botnet configuration to botnet.json
Gracefully closes all SSH sessions
Exits the application
📸 Screenshots
Example output from the Botnet Control Panel:
![Image](https://github.com/user-attachments/assets/e273bdb2-7315-4b1f-8826-43582ae38102)

![Image](https://github.com/user-attachments/assets/75e7147d-4db0-4f27-b088-dd62768fe2ef)
![Image](https://github.com/user-attachments/assets/962a55ff-9d33-4f50-b149-d50681fca68e)

👨‍💻 Author
Koppoju Uday Kumr
🎓 B.Tech in CSE (Cybersecurity)
📧 Email: udaykumarkoppoju@gmail.com
🔗 GitHub

🔒 Use Responsibly
This tool is intended for learning, research, and authorized testing only.
Never use it without explicit permission on networks or systems you do not own.

🙋‍♂️ Contributing
Contributions are welcome! Feel free to fork this repo and submit pull requests.

Fork the repository
Create your branch (git checkout -b feature-name)
Commit your changes (git commit -am 'Add new feature')
Push to the branch (git push origin feature-name)
Open a Pull Request
License
This project is open-source and free to use by anyone for personal or educational purposes.
Feel free to modify, distribute, and use the code as long as proper credit is given to the original author, Koppoju Uday kumar.
