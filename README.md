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
sudo apt update && sudo apt install -y curl unzip libgomp1 screen
apt update && apt install -y curl unzip libgomp1 screen
```

## **Step 2: Download and Set Up the Node**
Clone the Fortytwo Node repository and extract the files:
```bash
mkdir -p ~/Fortytwo && cd ~/Fortytwo
curl -L -o fortytwo-console-app.zip https://github.com/Fortytwo-Network/fortytwo-console-app/archive/refs/heads/main.zip
unzip fortytwo-console-app.zip
cd fortytwo-console-app-main
```

## **Step 3: Automate Node Execution**
To ensure the node runs automatically, create a startup script:
```bash
echo '#!/bin/bash
cd ~/Fortytwo/fortytwo-console-app-main
screen -dmS fortytwo ./linux.sh' > ~/Fortytwo/start_node.sh
chmod +x ~/Fortytwo/start_node.sh
```

## **Step 4: Schedule Auto-Start with Cron**
Edit the crontab to run the node at system startup:
```bash
crontab -e
```
Add the following line at the end:
```bash
@reboot ~/Fortytwo/start_node.sh
```
Save and exit.

## **Step 5: Monitor and Manage the Node**
To check if the node is running:
```bash
cd ~/Fortytwo/fortytwo-console-app-main
screen -ls
```
To re-enter the session:
```bash
screen -r fortytwo
```
To stop the node:
```bash
screen -X -S fortytwo quit
```

---

This setup ensures your Fortytwo Node starts automatically upon system reboot and runs in the background. Let me know if you need further customization! 🚀
