# **Automating Fortytwo Node Deployment**
A decentralized AI network where every computer contributes to planetary-scale intelligence
## **Prerequisites**
Before setting up an automated Fortytwo Node, ensure your system meets the following requirements:
- **Operating System:** Ubuntu 20.04 / 22.04 (recommended)
- **Hardware:** At least 16GB RAM, SSD storage, and a stable internet connection
- **Dependencies:** `curl`, `unzip`, `libgomp1`, `screen`

## **Step 1: Install Required Dependencies**
Run the following command to install necessary packages:
```bash
apt update && apt install -y curl unzip libgomp1 screen tmux
```

## **Step 2: Download and Set Up the Node**
Clone the Fortytwo Node repository and extract the files:
```bash
mkdir -p ~/FortytwoCLI && cd ~/FortytwoCLI
curl -L -o fortytwo-console-app.zip https://github.com/Fortytwo-Network/fortytwo-console-app/archive/refs/heads/main.zip
unzip fortytwo-console-app.zip
cd fortytwo-console-app-main
screen -S fortytwo or tmux new -s fortytwo
chmod +x linux.sh && ./linux.sh
screen -r fortytwo or tmux attach -t fortytwo
```
To stop the node:
```bash
screen -X -S fortytwo quit
Exit tmux Ctrl + B and D
```

---
This setup ensures your Fortytwo Node starts automatically upon system reboot and runs in the background. Let me know if you need further customization! 🚀
