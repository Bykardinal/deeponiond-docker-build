# What is DeepOnion (ONION)?
DeepOnion is a decentralized, multi-layered, privacy cryptocurrency that communicates with other nodes through the anonymous Tor network. DeepOnion uses x13 algorithms to secure the network. The brand logo is an onion with a key hole representing security and the use of the onion routing network. To ensure complete anonymity, all transactions are sent through the Tor network to protect and hide the physical location and the IP address of the wallet users from tracking.

DeepOnion launched a number of other blockchain technologies and platforms, such as:

DeepVault – allows you to register digital files safely on the DeepOnion blockchain, to be verified for authenticity with the file owner.

DeepSend – provides anonymous and untraceable payments through the use of multi-signatures.

VoteCentral - A blockchain dependent voting platform for the DeepOnion community to decide the future development and to help promote the project.

ONION cryptocurrency has the following technical parameters:
The mechanism for achieving consensus is a hybrid, combining both Proof-of-Work and Proof-of-Stake; hash algorithm – X13;
the number of blocks to confirm the transaction – 5;
final issue volume – 25 million coins;
block generation time - with PoS – 60 seconds, with PoW – 240.

# Why do I need this repository?
This repository is used to automatically build the DeepOnion docker images on the dockerhub platform. Our dockerhub account is connected with this repository and will update automatically. After we release a new version of the DeepOnion wallet, our dockerhub will automatically get the latest version of the image. Also this repository may be useful for experienced people who need a custom image, or will edit dockerfile after cloning repo and before building docker image.

# Why do I need a docker image built from this code?
With the Docker image, you can run the DeepOnion wallet in an isolated container. It maybe useful for cryptocurrency exchanges, for cryptocurrency wallets, and for mining pools. You don't need to know how to build wallet from the source code, just run a few commands and you will have a secure, trusted and ready to use wallet.

# How use docker images
You have two ways. You can download the images from dockerhub, or you can clone this github and build docker images on your machine. For building image from github code you should have installed git and docker in your system.


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
To work with a docker container you should know container id. Run the following command to see all your containers:

    sudo docker ps -a
After this you can send any command to specific container and work with DeepOnion wallet. As example:

    sudo docker exec <containerID> DeepOnion-cli getnetworkinfo
or

    sudo docker exec <containerID> DeepOnion-cli help
Will list all the available commands. They are similar to Bitcoin-cli, so if you have experience with Bitcoin-cli, you have experience with DeepOnion-cli.

###     How to launch DeepOnion docker container using custom working dir?
     
    sudo docker run -d -v $HOME/.DeepOnion:/root/.DeepOnion deeponionteam/deeponiond-docker-build:tag


# License

The MIT License (MIT)

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.


