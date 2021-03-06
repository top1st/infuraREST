# INFURA.IO REST JSON-RPC

Simple python client side REST-API implementing eth node JSON-RPC calls to infura.io.  No exceptions/exception classes considered for the first version (on their way).


# Account Registration and Project Creation  
Before using **infura.py** and running **test_infura.py** successfully you will need to complete the following two steps:

1) Account Registration : infura accnt. registration [here](https://infura.io).  
2) Project Creation   

After the above two steps have been successfully taken, migrate to your project dashboard and get the project id and project secret. Navigate to **test_infura.py** copy and paste both to their corresponding variables.  

#  Code Overview
## infura.py  
This is the client side REST code. Implemented here are the JSON-RPC known to an ETHEREUM node. On a successful return, the data requested can be found in the key result in the returning dictionary. If an error occurs, the results tag will not be shown in the returned requests object but replaced with an error tag.  

For more documentation on functions and their params I suggest taking a closer look at the docs page [here](https://infura.io/docs).

## test_infura.py
A simple unit test calling all the functions (with the exception of **eth_sendRawTransaction** and **eth_submitWork**) in the file **infura.py**.

# Using infura.py

Creating and using an infura type:

    import infura as inf
    _project_id     = "put your project id here"
    _project_secret = "put your project secret here"
    ...

    remote_node = inf.INFURA( _project_id, _project_secret )
    print("Current Block Number : {}".format( remote_node.get_block_number() ))    

***Note***  You may also specify the network you would like to gather information on through the node. This can be done by specifying the **_network** parameter in the INFURA constructor.
