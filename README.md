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
- Step 1. Claim by web  100 faucet (Paste address, email, code verify email) pero kailangan mo ng 41 days to get 4100 test token so proceed to step 2.
- https://cess.network/faucet.html
- Step 2. Send your address to discord cess, tell the mods you want to run node storage. if they asking how much TB u have just reply fuck off HAHA (I have 2 TB and am willing to contribute.)
- https://discord.com/invite/cess


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

## Here are the questions for the setup, just follow below.

- Enter cess node mode from 'authority/storage/rpcnode' (current: authority, press enter to skip): storage

- Enter cess storage listener port (current: 15001, press enter to skip): (enter only)

- Start configuring the endpoint to access Storage-Miner from the internet

- Try to get your extranet IP …
- Your Storage-Miner endpoint is http://xxx.xxx.xxx.xxx:15001 Do you need to automatically detect extranet address as endpoint? (y/n) y

- Enter cess rpc ws-url (current: local-chain, to use an external chain, type WS-URL directly, or press enter to skip): 
    ```sh
    wss://testnet-rpc.cess.cloud/ws/
    ```


- Enter cess storage earnings account: "cX..(Enter your reward address, wallet-2)"

- Enter cess storage signature account phrase: "(Enter your mnemonic, wallet-1)"

- Enter cess storage disk path (default: /opt/cess/storage/disk): (enter only)

- The directory: /opt/cess/storage/disk does not exist, do you need to create it for you? (y/n) y

- Enter cess storage space, by GB unit (current: 300, press enter to skip): "250 (adjust your storage size)"

- Enter the number of CPU cores used for mining; Your CPU cores are 4
- (current: 0, 0 means all cores are used; press enter to skip): 4

- Enter the staking account if you use one account to stake multiple nodes (if it is the same as the signature account, press enter to skip): (enter only)

- Enter the TEE worker endpoints if you have any (separate multiple values with commas, press enter to skip): (enter only)

- ## If you see 'Set configurations successfully,' your setup is working.

- 6.Start CESS storage node
    ```sh
    cess start
    ```
- 7.Check CESS Chain Sync Status (sync block may be 1-2 days)
    ```sh
    docker logs chain
    ```
![image](https://github.com/user-attachments/assets/3113cf09-5c11-4df3-af17-4e5c3af1cef3)

- 8.View storage node status (wait for the copy block to complete)
    ```sh
    cess miner stat
    ```
![image](https://github.com/user-attachments/assets/89780030-1c5b-4cad-a245-13961e39b2d1)

## DONE
















