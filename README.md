* A multi-threaded banking web server with thread-pooling implemented in Java.

* This web server accepts the following requests from HTTP clients -
a) Request to create bank accounts
b) Request to log transactions and update account balances
c) Request to check account balance
d) Request to delete bank accounts.

* Maintains the integrity of account balance data of bank accounts by keeping the data structure thread-safe and by tracking transactions.

* For the sake of simplicity, this project uses a simple HashMap to maintain account balance data. 
But in the real world, such data should be maintained using persistent data holders like databases, file systems, etc.

* Thread limit and server port must be registered in the webserver.properties file.

* Input format expected for the various business operations:

a) Create bank accounts : Requires account Number
Example: To create account with account number '1'

PUT HTTP/1.1
Host: localhost:8080
Cache-Control: no-cache

1

b) Log transactions and update account balances : Requires transaction information - account No, transaction type, amount
Example: To log a transaction of $5000 CREDIT by account No '1'

POST HTTP/1.1
Host: localhost:8080
Cache-Control: no-cache

1 CREDIT 5000

c) Check account balance : Requires account No
Example: To check account balance of account No '1'

GET /account/1 HTTP/1.1
Host: localhost:8080
Cache-Control: no-cache

d) Delete bank account : Requires account No
Example: To delete account with account No '1'

DELETE HTTP/1.1
Host: localhost:8080
Cache-Control: no-cache

1 

* For the sake of simplicity, this server accepts HTTP input in the form of raw text, with the attributes separated by whitespace. 
Ideally, a more structured format such as XML or JSON should be used for this.
