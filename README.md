Copyright (c) 2009-2019 Bitcoin Developers
Copyright (c) 2013-2019 Darkcoin Developers
Copyright (c) 2019 Jebitcoin Developers

What is Jebitcoin?
----------------
http://www.jebitcoin.com

Jebitcoin (JBT) is a peer-to-peer and business-to-business cryptocurrency designed 
with a long-term vision in mind. We are determined to create a resilient digital 
currency that will play a pivotal role in the digital finance macrocosm of the 
future due to being built upon solid programming design and advanced financial 
technology with genuine usability and merchant integration.

Jebitcoin is based on darkcoin and bitcoin and uses X11 as proof-of-work algorithm.

 - 1 minute block target
 - 99999999 total coins
 - 20000.007 coins per block (till 1000th Block) == 20.0000072% ~~ 20% 
 - 9 coins per block (till 8888888th Block) == 79.9999928% ~~ 80% 
 - Reward Maturity: 21 blocks
 - 1 Day or 10000 blocks to retarget difficulty
 - P2P Port: 78950
 - RPC Port: 78952


License
-------

Jebitcoin is released under the terms of the MIT license. See `COPYING` for more
information or see http://opensource.org/licenses/MIT.


Get Started
-----------

1. For Linux: You can use both GUI and CLI version of Jebitcoin depending upon your needs.

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

Once you have installed all dependencies, next step is to give read write and execute permissions to Jebitcoin folder. For that, go to the directory where Jebitcoin folder is located and then do:

sudo chmod -R 777 Jebitcoin/


 1.3 Compilation

After sucessfully giving all permissions, go to Jebitcoin folder and run:

cd src && make clean -f makefile.unix && make -f makefile.unix

It will take a while depending upon your system's hardware configuration (RAM and Processor)


 1.4 Running Jebitcoin CLI

Once compilation successfully ends, you can run Jebitcoin daemon with following steps:

a) Make sure you are in src folder of Jebitcoin ( your_directory/Jebitcoin/src )
b) Run: ./Jebitcoin -daemon
c) The above comamnd will create "data directory for Jebitcoin"(.Jebitcoin folder) in your home folder. And will flash an error message:

(The error message flashes for the first time only, not for subsequent uses)

Error: To use the "-daemon" option, you must set a rpcpassword in the configuration file:
/home/your_linux_username/.Jebitcoin/Jebitcoin.conf
It is recommended you use the following random password:
rpcuser=Jebitcoinrpc
rpcpassword=some_long_password
(you do not need to remember this password)
The username and password MUST NOT be the same.
If the file does not exist, create it with owner-readable-only file permissions.

d) Run: touch /home/your_linux_username/.Jebitcoin/Jebitcoin.conf
e) Run: nano /home/your_linux_username/.Jebitcoin/Jebitcoin.conf
NOTE: Replace "your_linux_username" in above commands with your own linux username

f) Copy rpc credentails from error message to Jebitcoin.conf file and save.
g) Run: ./Jebitcoin -daemon ( This time there won't be any error message )
h) Run: ./Jebitcoin getinfo (To check conenction status, blocks and other information)
You have a running CLI wallet now

i) Refer to cli-commands for more information.

 1.5 Running Jebitcoin-qt (Linux GUI Wallet)

After successfully comiling Jebitcoin CLI, you can proceed for Jebitcoin-qt Wallet

a) Make sure you are in Jebitcoin's root directory ( your_directory/Jebitcoin)
b) Run: qmake
b) Run: make
c) You will see GUI wallet being complied on your screen, it will take some time.
d) Once compilation ends, Run: ./Jebitcoin-qt
e) You will see an Jebitcoin-qt icon in your Jebitcoin's root Directory, use that for subsequent uses.

Enjoy your GUI wallet


2. For Windows: GUI client is available.

2.1 Use the setup file to install Jebitcoin GUI Wallet

2.2 Default Location of Jebitcoin's root Directory in Windows is:
    
    32-bit: Program Files/Jebitcoin
    64-bit: Program Files (x86)/Jebitcoin

2.3 Data Directory is located at: Users/your_windows_user/AppData/Roaming/Jebitcoin


3. CLI Commands (for linux)

3.1 Make sure you are in src folder of Jebitcoin ( your_directory/Jebitcoin/src )

3.2 Run daemon: ./Jebitcoin -daemon
    (It will take some time, press Enter key if it's too long)

3.3 Run given CLI commands to use your CLI Wallet:

a) Check you CLI Wallet's Status: ./Jebitcoin getinfo

b) Check your Wallet's Balance: ./Jebitcoin getbalance

c) Check number of Nodes you are connected to: ./Jebitcoin getconnectioncount

d) Display Detailed information of Connedted Nodes: ./Jebitcoin getpeerinfo

e) Generate New Address for Wallet: ./Jebitcoin getnewaddress

f) Send some JBT amount to an JBT address: ./Jebitcoin sendtoaddress <JBT Address> <Amount>
   example: ./Jebitcoin sendtoaddress iVFWg6saZ4L6yvaJso14y2YpRD5hGPNVEL 0.999

g) View all transactions in your wallet: ./Jebitcoin listtransactions

h) Encrypt CLI and GUI Wallet: ./Jebitcoin encryptwallet <passphrase>
   example: ./Jebitcoin encryptwallet thehard*&password!!

i) Unlock CLI Wallet for given time (in seconds): ./Jebitcoin walletpassphrase <passphrase> <timeout>
   example: ./Jebitcoin walletpassphrase theahard*&password!! 90

j) Change Wallet Passphrase: ./Jebitcoin walletpassphrasechange <oldpassphrase> <newpassphrase>
   example: ./Jebitcoin walletpassphrase thehard*&password!! thenew%^password

