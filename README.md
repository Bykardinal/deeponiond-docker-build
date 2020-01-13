# What is DeepOnion ?
What is DeepOnion (Onion)? DeepOnion is an anonymous cryptocurrency operating through a secret Internet network Tor and on the X13 algorithm. The bulb with the keyhole on the emblem of DeepOnion hints at the onion routing system used - the technology of anonymous data transfer in a computer network.

To ensure complete anonymity, all transactions are carried out through the Tor network, which completely hides the user's IP address. This not only provides a high level of confidentiality but also negates the ability to track payments. In addition, the project uses a number of other technologies:

DeepVault – allows you to store information safely in the DeepOnion blockchain, while the ability to change it is completely absent.

DeepSend – provides anonymous and non-tracked transactions through the use of multi-signatures. ONION cryptocurrency has the following technical parameters:

the mechanism for achieving consensus is a hybrid, combining both Proof-of-Work and Proof-of-Stake; hash algorithm – X13;

the number of blocks to confirm the transaction – 5;

final issue volume – 25 million coins;

block generation time - with PoS – 60 seconds, with PoW – 240.

# For what need this repository
This repository need for autobuilding DeepOnion docker images on dockerhub platform. Our dockerhub account connected with this repository and tracking updates. After we will release new version of wallet, our dockerhub will get new version of image.
Also this repository may be useful for experienced people who need custom image and will edit dockerfile after cloning repo and before building docker image.

# For what need docker image built from this code
With Docker image, you can run DeepOnion wallet in isolated container. It maybe useful for cryptocurrency exchanges, for cryptocurrency wallets, for mining pools. And you no need to know how to build wallet from source code, just few commands and you have secure, trusted and ready to use wallet.

# How use docker images
You have two ways. You can download images from dockerhub, or you can clone this github and build docker images on your machine.

For building image from github code you should have installed git and docker in your system.

### Commands for building image
    $ git clone https://github.com/deeponion/deeponiond-docker-build/
    $ sudo docker build -t deeponion/deeponiond-docker-build:version deeponion-docker-build
    
After docker will finish building new image you can check docker images and will see new image

    $ sudo docker images
    $ sudo dun -d <image/name:tag>

### Commands for Downloading ready to use images built by dockerhub

    sudo docker run -d deeponionteam/deeponiond-docker-build:tag
After running this command, docker will automatically load ready to use image and will launch it. DeepOnion wallet will start syncing process.

# How work with DeepOnion docker container after lauch
for working with docker container you should know container id. Run bellow command to see all your containers

    sudo docker ps -a
after this you can send any command to specific container and work with DeepOnion wallet. As example:

    sudo docker exec <containerID> DeepOnion-cli getnetworkinfo
or

    sudo docker exec <containerID> DeepOnion-cli help
you will get all possible commands list. They same with Bitcoin-cli, so if you have experience with Bitcoin-cle, you have experience with DeepOnion-cli.

### how launch DeepOnion docker container with using custom working dir.

    sudo docker run -d -v $HOME/.DeepOnion:/root/.DeepOnion deeponionteam/deeponiond-docker-build:tag



