# email-server
Email server and client made using Java

This was made as a school project, and can be used by anyone affiliated with the TDSB (Toronto District School Board).

Please read "How to run the email server.txt" to read how the server works.

Before running, there must be three files; _account.dat, _message.dat and _available.dat. These files will store account data, message data and deleted message data, respectively.

## General Tips on Running the Email Server:
- The email server and client can run on one computer, just note that you need to run both files at the same time.

- _messages.dat is the file that holds ALL MESSAGES STORED. It will not contain deleted messages.
- _accounts.dat will hold all known account names. account names are stored as 9 bits. if the account name is less than 9 bits, a variable amount of 0's will be added to the end.
- all info is passed to message/account files and then re-read from there.
- The messages are objects structures that contain message data in them. They conform to the Record object when inputted to the file. Messages are structures that are made up of Records.
- Records are of 84 bits size. They are fixed size, and their total sizes cannot be changed. Messages greater than one record size will be split into multiple records and run.
- Note that Records will always be added to the end of the file unless there are spaces/gaps in records within the message file.
These gaps come from deleting messages/records.
- Deleting a message with multiple records will delete all affiliated records.	
- Deleted record spaces will be saved as a "record number" in the available list. 
- available list is a linked list that contains all deleted record spaces.
- available list also chooses the MODE of the writing method. If the mode is APPEND, that means available list is empty and thus
the writing methods will write the message to the end of the file.
- If the mode is MODIFY, then the writing method will first write the message's records to empty record spaces within the file
before writing to the end of the file.
- The file Globals is a program with variables crucial for all files. Variables are stored there for re-usability and effeciency.
- Likewise, the file Utils has various methods used in multiple programs. They are stored there for cleanliness and effeciency.
- Like its name says, FileIO is the program that controls the opening and closing of the data files.
