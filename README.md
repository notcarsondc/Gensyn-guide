# Gensyn-guide
ALL GUIDE OF GENSYN AND ERRORS SOLUTION
**ALL CMDS CAN BE COPY-PASTE**

---

## 🛠️ Prerequisites

### FOR **VPS/WSL**:


```bash
sudo apt update && sudo apt install -y python3 python3-venv python3-pip curl wget screen git lsof
```

## 🟩 Install Node.js

### FOR **VPS/WSL**:

```bash
curl -fsSL https://deb.nodesource.com/setup_20.x | sudo -E bash -
sudo apt update && sudo apt install -y nodejs
```


---

## 🧶 Install Yarn

### FOR **VPS/WSL**:

```bash
curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | sudo apt-key add -
echo "deb https://dl.yarnpkg.com/debian/ stable main" | sudo tee /etc/apt/sources.list.d/yarn.list > /dev/null
sudo apt update && sudo apt install -y yarn
```

---

## 🔢 Check Versions

```bash
node -v
npm -v
yarn -v
```

---

## 📦 Install Cloudfared 

```bash
yes | sudo apt install ufw -y && sudo ufw allow 22 && sudo ufw allow 3000/tcp && yes | sudo ufw enable && wget -q https://github.com/cloudflare/cloudflared/releases/latest/download/cloudflared-linux-amd64.deb && sudo dpkg -i cloudflared-linux-amd64.deb
```
---

## 🧬 Clone RL-Swarm Repository

```bash
git clone https://github.com/gensyn-ai/rl-swarm.git
```

---

## 🖥️  Create a Screen Session (for VPS)

```bash
screen -S gensyn
```

---

## 📂 Navigate to RL-Swarm Directory

```bash
cd rl-swarm
```


---

## 🏗️ Create & Activate Python 

```bash
python3 -m venv .venv
source .venv/bin/activate
```
---

## 🚦 Run the Swarm Node

```bash
./run_rl_swarm.sh
```

Follow the prompts:

1. **Would you like to connect to the Testnet?**  
    Enter: `Y`

2. **Which swarm would you like to join (Math (A) or Math Hard (B))?**  
    Enter: `a`

3. **How many parameters (in billions)?**  
    Choose: `1.5/7`

---

## 🌐 Login

- **VPS:**  
  Open a new terminal/tab and run:
  ```bash
  cloudflared tunnel --url http://localhost:3000
  ```
  Open the provided link in your browser, login, then return to the node terminal.

---

## 🆔 Save Your Credentials

- When prompted:  
  **Would you like to push models you train in the RL swarm to the Hugging Face Hub?**  
  Enter: `N`
  
- After login, your **Username** and **Peer ID** will appear in the terminal.  
  **Save them!**

---

## 🖥️ VPS Users: Detach Screen

Press `Ctrl+A+D` to keep your node running in the background.

To see or reattach the node 

```bash
screen -r gensyn
```

---

## 🏆 Check Rewards

- Visit [@GensynReward_bot](https://t.me/GensynReward_bot) on Telegram.
- Send `/add` and then your **Peer ID** for updates.

---

