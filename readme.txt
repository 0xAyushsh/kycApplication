Introduction

The manual process involved with KYC, or more specifically the process of verifying each and every employee, or analogously each and every customer that comes by your store, is, naturally, a difficult task for any organization, big or small. And, adding to this fact, the vulnerabilities involved in this process has lead to many financial and integrity issues.

Know Your Customer (KYC) processes are solutions adopted by companies across a wide range of industries to identify and verify customers in order to authenticate them for specific privileges. KYC verification is a pain point for organizations because it is often costly, inefficient, and a source of frustration for customers.



Network Architecture-

3 Banks network : SBI Bank, ICICI Bank, CITI Bank.
Peers : peer0.sbibank.example.com, peer0.icicibank.example.com, peer0.citibank.example.com
One Orderer Organization
Fabric CA for Certificate generation.
Postman for generating requests to backend
Node.js for backend


Application Flow-

To Start the network go to kyc-network folder and run (on terminal) :
./network.sh down (to remove any existing running network)
./network.sh up createChannel -c kycchannel -s couchdb -ca

Above commands will generate certificate using Fabric-CA and create a channel named ‘kycchannel’.

To deploy the chaincode on to the channel run the following command on terminal :
./network.sh deployCC -c kycchannel -ccp ../chaincode -ccn kyc_chaincode -ccl go

To run the backend server go to kycApp folder and run (on terminal) :
node app.js

Now user can send requests using Postman.