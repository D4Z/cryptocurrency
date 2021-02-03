# cryptocurrency
Simple Cryptocurrency Implementation in Python

Program Documentation 
 
This program consists of two python files, Transaction Manager.py and Block Miner.py, which have been developed with Python 3.6.5 using the hashlib and keyboard modules. It requires both modules to run.  
 


D-Coin Transaction Manager Program 
 
The transaction management program opens the transaction file, creating it if necessary, and loads previous transaction data. Users can add new transactions, list the previous transactions or search for transactions involving a specific user. If the user selects add transaction, they are prompted for the sender’s name, the receiver’s name and the transaction amount. This information is then written to the transaction file along with a timestamp. If the user selects l the system prints all transactions contained in the file. If the user selects s, they are prompted for a name and the system will print all transactions that contain that user. 
 


D-Coin Block Miner Program 
 
When the block mining program stats it loads the block chain data from the blockchain file, then looks at the transaction file size and records it. It then monitors the file size and when it changes, it loads the new transaction data, constructs the data to hash from the previous sha256 key, transaction data, index and nonce. It generates the SHA256 hash, then determines if the hash meets the acceptance criteria. For the hash to be accepted, the first 14 binary characters must be zero. When it finds the nonce that generates an appropriate key, the creates a new block with the transaction data, timestamp, previous hash, nonce and new hash. If now valid nonce is found after 50000 tries, the program uses the last hash tested. It then goes back to watching for new transactions. 
 
The program listens for a ‘q’ keypress, and if detected will exit the program. 
 


Known Issues 
 
The BlockMiner.py program may detect a q key press when it is minimised or doesn’t have focus. In 
Windows to avoid this they can be run side by side in an IDE such as PyCharm. On Linux, the Terminator terminal can be used to run both programs side by side to avoid this issue, however in this case it is important to launch TransactionManager.py first so the transaction file has the correct permissions. 
 
 
 
Program Usage Instructions 
 
If the keyboard or hashlib module have not been installed they can be installed with the commands: 
 
pip install keyboard 	or  	pip3 install keyboard  pip install hashlib  	or  	pip install hashlib (if required)  
 


Block Miner.py 
 
The block mining program can be executed by executing one of the following commands: 
 
python BlockMiner.py  
	python3 BlockMiner.py 	 
 
Note: On Linux the program must be run as root using sudo: 
sudo python BlockMiner.py 
sudo python3 BlockMiner.py 
 
To exit the program, type ‘q’. 
 


TransactionManager.py 
 
The transaction management program can be executed by executing one of the following commands: 
 
	python TransactionManager.py 	 
python3 TransactionManager.py 
 
New transactions can be added by typing ‘a’. 
You can view the list of transactions by typing ‘l’ 
You can search for all transactions that contain a user by typing ‘s’ To exit the program, type ‘q’ and hit enter. 
 


Batch Files 
 
The programs can be launched in windows using block-miner.bat and transaction-manager.bat, or on Linux using block-miner.sh and transaction-manager.sh 
