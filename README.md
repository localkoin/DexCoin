Copyright (c) 2009-2019 Bitcoin Developers
Copyright (c) 2013 Darkcoin Developers
Copyright (c) 2019 DexCoin Developers

What is DexCoin?
----------------
http://www.localkoin.io

DexCoin (DXC) is a peer-to-peer and business-to-business cryptocurrency designed 
with a long-term vision in mind. We are determined to create a resilient digital 
currency that will play a pivotal role in the digital finance macrocosm of the 
future due to being built upon solid programming design and advanced financial 
technology with genuine usability and merchant integration.

DexCoin is based on darkcoin and bitcoin and uses X11 as proof-of-work algorithm.

 - 1 minute block target
 - 99999999 total coins
 - 20000.007 coins per block (till 1000th Block) == 20.0000072% ~~ 20% 
 - 9 coins per block (till 8888888th Block) == 79.9999928% ~~ 80% 
 - Reward Maturity: 21 blocks
 - 1 Day or 10000 blocks to retarget difficulty
 - P2P Port: 18775
 - RPC Port: 18776


License
-------

DexCoin is released under the terms of the MIT license. See `COPYING` for more
information or see http://opensource.org/licenses/MIT.


Get Started
-----------

1. For Linux: You can use both GUI and CLI version of DexCoin depending upon your needs.

We recommend any stable version of Ubuntu 16.04


 1.1 Installing Dependencies 

Open the terminal and run following commands one by one:


sudo apt-get install git

sudo apt-get install build-essential libtool autotools-dev automake pkg-config libssl-dev libevent-dev bsdmainutils

sudo apt-get install libboost-system-dev libboost-filesystem-dev libboost-chrono-dev libboost-program-options-dev libboost-test-dev libboost-thread-dev

sudo apt-get install libboost-all-dev

sudo apt-get install software-properties-common

sudo add-apt-repository ppa:bitcoin/bitcoin

sudo apt-get update

sudo apt-get install libdb4.8-dev libdb4.8++-dev

sudo apt-get install libminiupnpc-dev

sudo apt-get install libzmq3-dev

sudo apt-get install libqt5gui5 libqt5core5a libqt5dbus5 qttools5-dev qttools5-dev-tools libprotobuf-dev protobuf-compiler 

sudo apt-get install libqt4-dev libprotobuf-dev protobuf-compiler


 1.2 Giving Permissions

Once you have installed all dependencies, next step is to give read write and execute permissions to DexCoin folder. For that, go to the directory where DexCoin folder is located and then do:

sudo chmod -R 777 DexCoin/


 1.3 Compilation

After sucessfully giving all permissions, go to DexCoin folder and run:

cd src && make clean -f makefile.unix && make -f makefile.unix

It will take a while depending upon your system's hardware configuration (RAM and Processor)


 1.4 Running DexCoin CLI

Once compilation successfully ends, you can run DexCoin daemon with following steps:

a) Make sure you are in src folder of DexCoin ( your_directory/DexCoin/src )
b) Run: ./DexCoin -daemon
c) The above comamnd will create "data directory for DexCoin"(.DexCoin folder) in your home folder. And will flash an error message:

(The error message flashes for the first time only, not for subsequent uses)

Error: To use the "-daemon" option, you must set a rpcpassword in the configuration file:
/home/your_linux_username/.DexCoin/DexCoin.conf
It is recommended you use the following random password:
rpcuser=DexCoinrpc
rpcpassword=some_long_password
(you do not need to remember this password)
The username and password MUST NOT be the same.
If the file does not exist, create it with owner-readable-only file permissions.

d) Run: touch /home/your_linux_username/.DexCoin/DexCoin.conf
e) Run: nano /home/your_linux_username/.DexCoin/DexCoin.conf
NOTE: Replace "your_linux_username" in above commands with your own linux username

f) Copy rpc credentails from error message to DexCoin.conf file and save.
g) Run: ./DexCoin -daemon ( This time there won't be any error message )
h) Run: ./DexCoin getinfo (To check conenction status, blocks and other information)
You have a running CLI wallet now

i) Refer to cli-commands for more information.

 1.5 Running DexCoin-qt (Linux GUI Wallet)

After successfully comiling DexCoin CLI, you can proceed for DexCoin-qt Wallet

a) Make sure you are in DexCoin's root directory ( your_directory/DexCoin)
b) Run: qmake
b) Run: make
c) You will see GUI wallet being complied on your screen, it will take some time.
d) Once compilation ends, Run: ./DexCoin-qt
e) You will see an DexCoin-qt icon in your DexCoin's root Directory, use that for subsequent uses.

Enjoy your GUI wallet


2. For Windows: GUI client is available.

2.1 Use the setup file to install DexCoin GUI Wallet

2.2 Default Location of DexCoin's root Directory in Windows is:
    
    32-bit: Program Files/DexCoin
    64-bit: Program Files (x86)/DexCoin

2.3 Data Directory is located at: Users/your_windows_user/AppData/Roaming/DexCoin


3. CLI Commands (for linux)

3.1 Make sure you are in src folder of DexCoin ( your_directory/DexCoin/src )

3.2 Run daemon: ./DexCoin -daemon
    (It will take some time, press Enter key if it's too long)

3.3 Run given CLI commands to use your CLI Wallet:

a) Check you CLI Wallet's Status: ./DexCoin getinfo

b) Check your Wallet's Balance: ./DexCoin getbalance

c) Check number of Nodes you are connected to: ./DexCoin getconnectioncount

d) Display Detailed information of Connedted Nodes: ./DexCoin getpeerinfo

e) Generate New Address for Wallet: ./DexCoin getnewaddress

f) Send some DXC amount to an DXC address: ./DexCoin sendtoaddress <DXC Address> <Amount>
   example: ./DexCoin sendtoaddress iVFWg6saZ4L6yvaJso14y2YpRD5hGPNVEL 0.999

g) View all transactions in your wallet: ./DexCoin listtransactions

h) Encrypt CLI and GUI Wallet: ./DexCoin encryptwallet <passphrase>
   example: ./DexCoin encryptwallet thehard*&password!!

i) Unlock CLI Wallet for given time (in seconds): ./DexCoin walletpassphrase <passphrase> <timeout>
   example: ./DexCoin walletpassphrase theahard*&password!! 90

j) Change Wallet Passphrase: ./DexCoin walletpassphrasechange <oldpassphrase> <newpassphrase>
   example: ./DexCoin walletpassphrase thehard*&password!! thenew%^password

