# BTAD-multi-masternode
BTAD multi masternode (this is not the official script , use at your own risk)  

Information:  
-> This one is forked from here:https://github.com/ebe222/BTAD-multi-masternode  

because I had issues in executing the orignal script on my vps.  
The issues were:  

1.) It was not possible to bind on adress 192.168.1.X. (I changed it in this script to 127.0.0.X)  
2.) The variable 'dev2' was always empty and therefore the command 'ip addr del ...' and 'ip addr add ...' in the script
    were not working.   
3.) The number of masternodes could not be greater than 9. (At least on my computer)  
    Now no arguments are needed anymore. And the script stops adding new masternode if user just press return key when
    the script is asking about masternode key.  
    This means:  
    1.) User executes the script.  
    2.) Prompt is shown for adding new masternode key.   
    3.) User insert the new masternode key now.  
    4.) This new masternode will be prepared and then the user is asked again about next new masternode key.  
    5.) This is repeated over and over again.  
    6.) The user can stop adding new masternode key by just pressing the enter-key without adding some text.   
    




```bash
git clone https://github.com/DevLooper9325/BTAD-multi-masternode.git
cd BTAD-multi-masternode
chmod +x multinode_SAP.sh
```
Execute the script:
```bash
./multinode_SAP.sh
```
it will asks you for the masternode private key, go to your wallet console and type: 
```bash 
masternode genkey
``` 
remember that each nodes needs a different key.
-> If you just press the enter-key, without providing new masternode-key then the script knows that you do not want to
add more masternodes.  


after everything is done , start it up 
```bash 
./start_multinode.sh
```

Currently the commands only works while you are inside the folder that you cloned, current commands:
```bash 
./start_multinode.sh # start the masternodes
./stop_multinode.sh # stop the masternodes
./mn_status.sh # check the state of the masternodes
./mn_getinfo.sh # receive info of the wallet server (can check blocks progress as well from here)
```

reminder that if you restart your VPS you need to use the above command to start the masternodes servers 
# Credits
script based on https://github.com/ebe222/BTAD-multi-masternode 
and
https://github.com/methuselah-coin/MultiNode_IPv4

 
