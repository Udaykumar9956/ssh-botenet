🧠 Botnet Control Panel
A Python-based SSH botnet command-and-control system, designed strictly for educational and authorized penetration testing purposes. This tool allows you to connect to multiple SSH-enabled machines (bots) and execute commands, interact via bash, or launch simulated DDoS attacks on a test server.

⚠️ Legal Disclaimer:
This project is intended strictly for educational purposes and authorized network testing only.
Do NOT use this tool on any system or network without explicit permission from the owner.
Unauthorized use may violate computer crime laws and result in severe consequences.

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
bash
Copy
Edit
├── botnet.py         # Main control panel for managing bots
├── server.py         # Dummy target server to test DDoS modules
├── botnet.json       # Auto-generated file storing bot details
└── README.md         # Documentation
🧩 Dependencies
Library	Purpose
scapy	Packet crafting (used in DDoS module)
pexpect	SSH interaction via pxssh
colorama	Colorful terminal outputs

🚀 Usage
1. Start the Dummy Test Server
Run on your target machine:

bash
Copy
Edit
python server.py
🛠️ Default port: 8080 (changeable in the script)

2. Launch the Botnet Control Panel
Run on your Kali Linux or attacking machine:

bash
Copy
Edit
sudo python3 botnet.py
⚠️ sudo is required for raw packet crafting with Scapy.

📋 Menu Options
1. List Bots
Displays currently connected bots with:

IP Address

Port

Username

Connection Status (Connected / Disconnected)

2. Run Command
Broadcast a single shell command to all bots.

Example:

bash
Copy
Edit
$ Enter a command to run: uname -a
3. Bash Mode
Interactive bash-like shell mode.
Commands are sent to all bots one by one.

bash
Copy
Edit
bash>>> whoami
bash>>> ls /home
Type exit to return to main menu.

4. Add Bot
Add a new SSH-based bot:

IP Address

Port (default: 22)

Username

Password

On success, the bot is saved to botnet.json.

5. DDoS (Testing Only)
🚨 Use only on authorized systems like the included server.py.

Attack types:

SYN Flood

UDP Flood

ICMP Flood

TCP Connect Flood

HTTP GET Flood

Multi-vector (SYN + UDP + ICMP)

You’ll be prompted for:

Target IP and port

Attack type

Number of packets/requests

6. Exit
Saves configuration to botnet.json

Gracefully closes SSH sessions

Exits the application

📸 Screenshots
Include screenshots of your terminal running botnet.py and sample commands here.

👨‍💻 Author
Kasula Shiva
🎓 B.Tech in CSE (Cybersecurity)
📧 Email: shivakasula10@gmail.com
🔗 GitHub: github.com

🔒 Use Responsibly
This tool is intended for learning, research, and authorized testing only.
Never use it on networks or systems you do not own or have explicit permission to test.

🙋‍♂️ Contributing
Contributions are welcome!
Steps:

Fork the repository

Create a new branch:

bash
Copy
Edit
git checkout -b feature-name
Commit your changes:

bash
Copy
Edit
git commit -am 'Add new feature'
Push to GitHub:

bash
Copy
Edit
git push origin feature-name
Open a Pull Request

📄 License
This project is open-source and free to use for personal and educational purposes.
You may modify, distribute, and use the code as long as proper credit is given to the original author, Kasula Shiva.
