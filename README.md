# Blockcast-Beacon-Node-Run-Guide

Blockcast is a decentralized content delivery network (CDN) that lets anyone contribute bandwidth and storage to speed up internet content delivery. Instead of relying on a few big CDN companies, Blockcast uses community-run nodes to deliver content locally, faster, and more efficiently—powered by DePIN, with economic incentives, privacy protections, and verifiable uptime.

---

## Rewards:

- By running a Blockcast beacon node, you earn points that will later convert into tokens.
- Blockcast has launched a 6-month campaign — top-performing nodes will receive a special NFT.

![image alt](https://github.com/CryptoGurujiOG/Blockcast-Beacon-Node-Run-Guide/blob/2f93f1b9e23d7ef1e1462536dc72cd57d0e951f5/Screenshot%201.png)

---

## Requirements:

- Minimum (2 vCPU, 2 GB RAM, 20 GB SSD, Stable Internet, Ubuntu 22.04)
- Recommended (4+ vCPU, 4+ GB RAM, 50+ GB SSD, Stable Internet, Ubuntu 22.04)
- More CPU, RAM, and Storage will improve performance and stability.

---

## Suggestion:

- You can run this node on your Windows PC, but I recommend using a VPS for better performance and uptime, especially if you're targeting the NFT reward.
- If you are only aiming to earn points, running it on your Windows device is fine.

---

# Steps 👇

- If you want to run verifier node on your pc/laptop, then install WSL using this 👉 [Guide](https://github.com/CryptoGurujiOG/Install-Ubuntu-on-Windows-using-WSL)
- If you want to run verifier node on a VPS then watch my video guide 👉 [Video](https://youtu.be/NK431xjj7yA)

### Update system & dependencies 
```
sudo apt update && sudo apt upgrade -y
```

```
sudo apt install ca-certificates curl gnupg lsb-release -y
```

### Add Docker Key & Install 
```
sudo mkdir -p /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg

```

```
echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] \
  https://download.docker.com/linux/ubuntu \
  $(lsb_release -cs) stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
```

```
sudo apt update
sudo apt install docker-ce docker-ce-cli containerd.io docker-compose-plugin -y
```

### Enable and start Docker 
```
sudo systemctl enable docker
sudo systemctl start docker
```


### Verify Installation
```
docker --version
docker compose version
```

### Clone Blockcast Repo 
```
git clone https://github.com/Blockcast/beacon-docker-compose.git
cd beacon-docker-compose
```

### Run Node 
```
docker compose up -d
```

![image](https://github.com/user-attachments/assets/484f3a4a-73fb-4fd5-ac65-205738039ce5)


### Check running container 
```
docker ps
```
![image](https://github.com/user-attachments/assets/4ef4d547-5ab2-41d2-8876-1b0da80b4e7b)


### Get Hardware ID & Challenge Key
Run this command to generate the values:
```
docker compose exec blockcastd blockcastd init
```

### You'll see output like `Hardware ID: your-hardware-id` and `Challenge Key: your-challenge-key`


## Register Your Node
* Visit Blockcast Website
* Signup/sign in using email
* Click the Manage Node and Register Node
* Paste your Hardware ID and Challenge Key
![image](https://github.com/user-attachments/assets/6199c816-d925-414b-b86f-a5a9f3c1c8dd)

### SUBMIT AND DONE! 

