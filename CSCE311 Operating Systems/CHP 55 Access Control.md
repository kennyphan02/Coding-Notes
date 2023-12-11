
- We know what our security goals are.
- Figure out if request fits within our security policy. This referred to as access control. we will determine which resources/services can be accessed by which parties in which ways under which circumstances. 


### Capability-based system vs access control list system
- Locks-and-keys example is a capability-based system
- access control list system is the bouncer letting certain people in based on the people on the list. 
- With a capability-based system, when a process wants to read and write a file, it hands a capability specific to that file to the system
- WIth a access control list system, the system looks up the user on the list only allowing access if the user is on the list. 

### ACLs for unix
Access Control Lists specify permissions for specific users on a given file/directory
- ACL information is stored in the extended attributes of a file/directory.
- getfacl = view ACL of a file/directory
- setfacl = modify ACL of a file/directory
- acl modes: each entry has specific permissions such as read/write/execute