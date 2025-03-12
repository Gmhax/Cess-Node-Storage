# Cess-Node-Storage
CESS is a project dedicated to developing a blockchain-based distributed cloud storage system. The emphasis lies in delivering reliable and efficient distributed storage services through adept management of resources using virtualization technology.


![image](https://github.com/user-attachments/assets/8bacd52b-c45d-4c9b-a6f6-587a736692f1)

# Prepare Before Install Node

- **Install Wallet extension Subwallet in chrome**

- https://chromewebstore.google.com/detail/subwallet-polkadot-wallet/onhogfjeacnfoofkfgppdlbmlmnplgbn

- **Create two wallets**

- Wallet-1 for signature & staking/claim faucet (don't forget to save pharse/mnemonic)
- Wallet-2 for reward address (don't forget to save pharse/mnemonic)
- Note: Store the address cess wallet-1 & wallet-2 prefix cX. (see picture below)
![image](https://github.com/user-attachments/assets/6cf353b1-d291-4b66-a733-eace0da5944c)

- **Claim faucet minimum 4100 (There are two ways to get a faucet.)**
- Claim by web  100 faucet (Paste address, email, code verify email)
https://cess.network/faucet.html
- Send your address to discord cess, tell the mods you want to run node storage. if they asking how much TB u have just reply fuck off HAHA (I have 2 TB and am willing to contribute.)


## Install Cess Node Storage on Ubuntu-Linux (VPS)
- 1.Update package & install wget, tar
    ```sh
    apt update && apt install wget tar -y
    ```
- 2.Install docker (If you haven't already, but if you have, just skip)
    ```sh
    sudo apt install apt-transport-https ca-certificates curl software-properties-common -y
    curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
    echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs)   
    stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
    sudo apt update
    apt-cache policy docker-ce
    sudo apt install docker-ce -y
    ```
- 3.Install cess client
   ```sh
    wget https://github.com/CESSProject/cess-nodeadm/archive/v0.6.0.tar.gz
    tar -xvzf v0.6.0.tar.gz
    cd cess-nodeadm-0.6.0/
    ./install.sh
    ```
- 4.Setup running network to testnet
    ```sh
    cess profile testnet
    ```
- 5.Setup config
   ```sh
    cess config set
    ```














