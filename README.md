# -Working-with-VPNs-
Understanding how a VPN works and demonstrate secure connectivity using ProtonVPN on Linux


## OVERVIEW

We’ll:

Install ProtonVPN CLI on my  Parrot OS

Log in & connect securely

Verify VPN works (IP change & encryption)

Capture required screenshots

Create your GitHub submission folder layout

## 1. Install ProtonVPN CLI

Open your terminal and run these commands one by one

```
`sudo apt update && sudo apt upgrade -y
 sudo apt install -y wget apt-transport-https gnupg lsb-release

```
<img width="791" height="221" alt="image" src="https://github.com/user-attachments/assets/d32fa950-e865-46ef-890b-83008c88f64e" />

Now Let's add the ProtonVPN official repository
use this cmd 

```

wget https://repo.protonvpn.com/debian/dists/stable/main/binary-all/protonvpn-stable-release_1.0.8_all.deb
sudo dpkg -i protonvpn-stable-release_1.0.8_all.deb
sudo apt update

```
<img width="1048" height="392" alt="image" src="https://github.com/user-attachments/assets/cfd94865-e2e4-4503-943e-a3b5ea408949" />


Now install ProtonVPN CLI tool:

```
  sudo apt install -y pipx
  pipx install protonvpn-cli
```
<img width="949" height="318" alt="image" src="https://github.com/user-attachments/assets/c23837e3-ba4c-41c5-8ea4-94bce915faa3" />

find proton VPN is downloaded on your system or not

Check where ProtonVPN is installed

Run this (exactly):
```
which protonvpn-cli
```

or if that shows nothing:
```

find ~/.local/bin -name "protonvpn*" 2>/dev/null

```
You’ll likely see a path like:

/home/etac/.local/bin/protonvpn-


That’s the correct executable — it just isn’t available for sudo.

<img width="949" height="404" alt="image" src="https://github.com/user-attachments/assets/01056494-c878-402f-b66b-1b71d1e5feb6" />


## Make it usable system-wide

Create a symbolic link to /usr/local/bin (which is in the root PATH):
```

sudo ln -s ~/.local/bin/protonvpn-cli /usr/local/bin/protonvpn-cli

```
Now check again:
```
protonvpn --version

```
You should see:

ProtonVPN v2.2.11

## Initialize and configure ProtonVPN

Now you can run it as root safely:

```
sudo protonvpn init

```
<img width="949" height="404" alt="image" src="https://github.com/user-attachments/assets/9dc4abd5-ec61-49a1-81ad-6b87b295a6c9" />

Then follow prompts:

Choose UDP protocol

Choose any country

Choose ProtonDNS

<img width="949" height="404" alt="image" src="https://github.com/user-attachments/assets/b50236c9-2cf5-4e1b-9a13-98e85f993c61" />

choose free plan

<img width="949" height="404" alt="image" src="https://github.com/user-attachments/assets/3fb76388-c38a-4a44-b647-af65914119e6" />

Then login:

```

sudo protonvpn-cli login your_protonvpn_username

```
<img width="949" height="230" alt="image" src="https://github.com/user-attachments/assets/69cac895-d910-4fe6-8bef-f5a48dd1049c" />

Follow prompts:

Choose protocol: UDP

Country: any (you can change later)

DNS: choose ProtonDNS (recommended
