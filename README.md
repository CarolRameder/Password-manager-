# Password-manager-

There are 2 C programs : server.c and client.c, that communicate with each other through socket, after the connection is made. The client can login and manage his passwords stored in the database Users.db, or create a new account that will be stored in the database. An user has specific username and password and cannot see other's data . The concurency of the appilication is made with fork(), and every new client that connects to the server is treated in a new child created from the parent process . 

Compile:
	- Server: gcc Server.c -o Server -lsqlite3
	- Client: gcc Client.c -o Client 

	Observation: Users.db must be left in the same folder, because Server.c has its pre-defined location saved . 

Run:
	- ./Server
	- ./Client
	Observation: Neither of them require parameters to run. Adress and port are already hardcoded.

Instructions:
        
    Select 1 or 2 (for signing in or signin up) 
    
    - 1 : the user has to type an user-name and password, if there is no match with the database, 
      the user can try again ( by typing 'y' ) or exit ( by typing 'n' ) . 
   
    - 2 : the user creates a new account 

	List of available commands:

    - 'print all': displays all information about all accounts
    - 'print by title input_title': displays all information about account with title = input_title
    - 'print by username input_username': displays all information about accounts with username = input_username
    - 'print by category input_category': displays all information about all accounts from category = input_category

    - 'add new': will allow you to fill each cell for a new account; insert 'x' for blank cells

    - 'remove all': removes all information about all accounts.
    (Requires confirmation : type 'y' to proceed or 'n' to turn back and type another command)

    - 'remove by title input_title': removes all information about account with title = input_title
    - 'remove by username input_username': removes all information about account with username = input_username
    - 'remove by category input_category': removes all information about accounts from category = input_category

    - 'print guide': prints guide again
    - 'exit': logs out and ends session
