How to setup a fabcoin test environment in your windows 10 environment.

#  Install Ubuntu 16.04  and  support package
Please refer doc/Build-unix.md to setup Ubuntu 16.04 and install support package.

## Install Ubuntu 16.04 with GUI desktop.

## Install other support package

Below is a quick shell-script to install package.

    sudo apt-get update
    sudo apt-get install git

    sudo apt-get install build-essential 
    sudo apt-get install autoconf libboost-all-dev libssl-dev libprotobuf-dev protobuf-compiler libqt4-dev libqrencode-dev libtool libevent-dev 
    sudo apt-get install python3-zmq libsodium-dev

    cd ~;
    wget http://download.oracle.com/berkeley-db/db-4.8.30.NC.tar.gz
    tar -xvf db-4.8.30.NC.tar.gz
    cd db-4.8.30.NC/build_unix
    mkdir -p build 
    BDB_PREFIX=$(pwd)/build
    ../dist/configure --disable-shared --enable-cxx --with-pic --prefix=$BDB_PREFIX
    make install
    cd ../..

## Install graphic card driver and OpenCL
Please refer doc/GPU-Mining.md and your graphic card specification to install proper drivers and OpenCL .


# Download Fabcoin and configure
    
## Download
Download Fabcoin Ubuntu 16.04 version from   http://13.59.134.49/en/testnet/Fabcoin-Ubuntu16.04-AMD.tar.Z, and extract it to $HOME/fabcoin 

## Configure Fabcoin

Set $HOME/.fabcoin as default data folder, config file is $HOME/.fabcoin/data/fabcoin.conf 
Please set below content in fabcoin.conf, to specific testnet.

    testnet=1 
    addnode=35.182.160.212
    addnode=13.59.134.49
    gen=1
    G=1
    allgpu=1

# Run 

## Fabcoin full node server 
Run $HOME/fabcoin/bin/fabcoind will start fabcoin full node server. 
Run fabcoind -h , will show all the running options.

## Run wallet program.
Run  $HOME/fabcoin/bin/fabcoin-qt  , which is under c:/workspace/fabcoin/bin.
Mostly, windows will warn you because you run this binary code which download from website, and you need allow fabcoin-qt run and access internet to make fabcoin-qt run.

## More about how to use  

Please refer fabcoin website and use guide.
