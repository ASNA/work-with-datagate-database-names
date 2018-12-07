## A command line utility to work with ASNA DataGate Database Names. 

Most AVR for .NET ASP.NET Websites need an ASNA DataGate Database Name created on the server. To avoid the need for installing any variation of Visual Studio on the server just for this purpose, you can use this command line utility to do so.

This utility lets you create, delete, or list DataGate Database Names for use with the IBM i.

>You must use a DOS command line opened with administrative rights to use this utility.

### Command line usage: 

To show top-level options:

`WorkWithDBNames --help` or `WorkWithDBNames` without any arguments shows the top level options. 

The first argument specifies the action: 

    WorkWithDBNames CREATE 
    WorkWithDBNames DELETE
    WorkWithDBNames LIST  

#### To create a database name: 

    WorkWithDBNames CREATE DBName Server Label User Password Pooling Port
    
Notes:
* To create a public database name (which you'll need on a Web server) prefix the name with `*Public/`.
* The DBName case will be assigned exactly as you enter it on the command line (Database names are not case sensitive).
* The Server argument can be a server name or IP address.
* The Label is a brief description name of the Database Name (ie 'Production IBMi').
* The PoolingTime must be specified in minutes. 
* The Port is the port DataGate uses on your IBM i and it must be four digits.
* To change a Database Name, delete it (see below) then create it again (with the changes).

> At this time this utility can only create Database Names that use the IBM i's secure password feature.

#### To delete a database name:

    WorkWithDBNames DELETE DBName 
    
Notes: 
* Database names aren't case sensitive.
* Nothing happens and no error message is shown if you attempt to delete an non-existent Database Name 

#### To list database names

    WorkWithDBNames LIST 
    
Notes:
    All public and private currently configured Database Names are listed. 
    
    