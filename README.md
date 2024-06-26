# Polymer Labs challenge 3 guide

You should have Gitpod and Github accounts. (pictorial representation will be attached below

1. Fork this repo https://github.com/polymerdevs/testnet-challenge-3-template

2. Head to gitpod.io , create an account if you haven't already then creat a workspace with the https url of the repo you forked.

3. Enter the commands below in the workspace terminal

## Deploy a UNIVERSAL PACKET from OPTIMISM

1. install git

```

`add-apt-repository ppa:git-core/ppa`

`apt update; apt install git`

```

2. clone template to your local machine

```

`git clone https://github.com/ava-world/first-xcounter`

```

3. install node.js

```

`sudo apt install curl`

`curl -s https://deb.nodesource.com/setup_18.x | sudo bash`

`sudo apt install nodejs -y`

`node -v`

```

install NVM

```

`curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.35.3/install.sh | bash`

```

```

`export NVM_DIR="$HOME/.nvm"`

`[ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh"`

`[ -s "$NVM_DIR/bash_completion" ] && \. "$NVM_DIR/bash_completion"`

```

```

`nvm`

```

```

`nvm install 20`

```

```

`nvm use 20`

```

4.install foundry

```

`curl -L https://foundry.paradigm.xyz | bash`

```

```

`source /root/.bashrc`

```

if using gitpod use this

```

`source /home/gitpod/.bashrc`

```

next is

```

`foundryup`

```

5. install just

```

`wget -qO - 'https://proget.makedeb.org/debian-feeds/prebuilt-mpr.pub' | gpg --dearmor | sudo tee /usr/share/keyrings/prebuilt-mpr-archive-keyring.gpg 1> /dev/null`

`echo "deb [arch=all,$(dpkg --print-architecture) signed-by=/usr/share/keyrings/prebuilt-mpr-archive-keyring.gpg] https://proget.makedeb.org prebuilt-mpr $(lsb_release -cs)" | sudo tee /etc/apt/sources.list.d/prebuilt-mpr.list`

`sudo apt update`

```

```

`sudo apt install just`

```

```

`cd first-xcounter`

`just install`

```

6. Setting up the private and API keys

We all know how to get our private keys, so that should be smooth and i advice you can use a burner wallet instead of your main.

Now to get the API keys, we need 4 keys, 2 from alchemy, one from optimism, and the last from base.

To get the alchemy API keys, head to [Alchemy Quickstart Guide](https://docs.alchemy.com/docs/alchemy-quickstart-guide), and create an account if you haven’t already, it will take you to your dashboard where you can create API keys for different chain. We are creating for sepolia base and optimism
(Pictorical representation will be provided below)

For Base API, head to [Base Sepolia - API keys | Blockscout](https://base-sepolia.blockscout.com/account/api-key), create an account if you havent already, and add API key.

For Optimism API, it is similar to base [OP Sepolia - API keys | Blockscout](https://optimism-sepolia.blockscout.com/account/api-key). Now to get drip from optimism faucet, [Superchain Faucet (optimism.io)](https://app.optimism.io/faucet), you have to Enable Github 2FA from settings to request for faucet. https://github.com/settings/security 

![cat.jpeg](https://res.cloudinary.com/wordy/image/upload/v1710997048/cat_lpue0i.jpg)

![cat1.jpeg](https://res.cloudinary.com/wordy/image/upload/v1710997049/cat1_cgi9ls.jpg)

![cat2.jpeg](https://res.cloudinary.com/wordy/image/upload/v1710997049/cat2_vpwnxd.jpg)

7. set up environment

```

`cp .env.example .env`

```

<l1>

EDIT .env file by imputing the right informations, an editor like vscode makes it easier to edit, its optional to use an editor though.

<l1/>

### IMPORTANT!!!!!

You are only making changes to line 2, 6, 7, 8,9. DO NOT COPY MINE JUST USE THE LINKS I PROVIDED TO GET YOUR KEYS AND EDIT THEM IN THE .env file

```

`nano .env`

```

<l1>

PRIVATE_KEY_1='YOUR_METAMASK_PRIVATE_KEY'

Add more if your project requires more private keys

API keys for developer tooling and infra

OP_ALCHEMY_API_KEY='YOUR_ALCHEMY_OP_SEPOLIA_API_KEY' link: https://docs.alchemy.com/docs/alchemy-quickstart-guide

BASE_ALCHEMY_API_KEY='YOUR_ALCHEMY_BASE_SEPOLIA_API_KEY' link: https://docs.alchemy.com/docs/alchemy-quickstart-guide

OP_BLOCKSCOUT_API_KEY='YOUR_OP_BLOCKSCOUT_API_KEY' link: https://optimism-sepolia.blockscout.com/account/api-key

BASE_BLOCKSCOUT_API_KEY='YOUR_ALCHEMY_BASE_SEPOLIA_API_KEY'  link: https://base-sepolia.blockscout.com/account/api-key

TENDERLY_TOKEN=''

<l1/>

after you can save using ctrl + x, then type "y", then enter.

then run  “just run-challenge-3” in the terminal

you would get this with different details

![Screenshot 2024-03-21 at 5.11.46 AM.png](https://res.cloudinary.com/wordy/image/upload/v1710997030/Screenshot_2024-03-21_at_5.11.46_AM_saicxy.png)

ctrl + click on the explorer URL which will take you to the scan

them click on logs

![Screenshot 2024-03-21 at 5.19.13 AM.png](https://res.cloudinary.com/wordy/image/upload/v1710997030/Screenshot_2024-03-21_at_5.19.13_AM_hmi0jm.png)

![Screenshot 2024-03-21 at 5.24.03 AM.png](https://res.cloudinary.com/wordy/image/upload/v1710997030/Screenshot_2024-03-21_at_5.24.03_AM_tgzxa9.png)

click on the circled text to take you to the contract.

![Screenshot 2024-03-21 at 5.25.25 AM.png](https://res.cloudinary.com/wordy/image/upload/v1710997031/Screenshot_2024-03-21_at_5.25.25_AM_msjpko.png)

click on logs again

”

![Screenshot 2024-03-21 at 5.25.35 AM.png](https://res.cloudinary.com/wordy/image/upload/v1710997030/Screenshot_2024-03-21_at_5.25.35_AM_bj0x1d.png)

THIS IS ONE OF THE SCREENSHOT YOU NEED TO POST ON THE PROOF CHANNEL

Now head to [IBC Explorer (polymer.zone)](https://sepolia.polymer.zone/packets) and check amond the recently delivered state and check if the **Ack Tx** matched the one in the scan.

![Screenshot 2024-03-21 at 5.31.52 AM.png](https://res.cloudinary.com/wordy/image/upload/v1710997030/Screenshot_2024-03-21_at_5.31.52_AM_uvsmju.png)

![Screenshot 2024-03-21 at 5.31.46 AM.png](https://res.cloudinary.com/wordy/image/upload/v1710997031/Screenshot_2024-03-21_at_5.31.46_AM_o6kdna.png)
