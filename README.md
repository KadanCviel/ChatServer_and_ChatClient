# Chat Server and Chat Client
There are two command line applications
 "client"" and "server" that write in c and server is implemented using "select" (or server can compile with "poll")

run the "server" then run the "clients"

install "cygwin" and select "gcc" package to be install also (as source for cygwin1.dll file, and for project compilations)

$./server.exe PORT_NUM    (if the parameter is missing it will use 8888 as PORT_NUM)
$./server.exe 7777
 use cygwin1.dll (take sygwin dll x86  and not 64_x86 dll) in the same folder. 
 from cmd> line.
 >server.exe PORT_NUM


for runninng:
type "cmd"
cd c:\MyData\Server_Client\Client
client.exe

type 
help:

NAME:new_name
Add the <new_name> to server list,
so registered clients will be able
to send messages to specific client
by using its <new_name>.

name:message
Will send the <message> to specific client <name>.

LIST:
Will show a list of all registered clients.

ALL:message
The <message> will broadcast to all registered clients.

ECHO:off/on
off (0) (default) server will not send back to client received chars as feedback.
on  (1)           server send back to client received chars as feedback.

CR:off/on
off (0)(default) dont show non printable chars, skip <CR><LF>.
on  (1)          show all recevied characters include <CR><LF>.

BYE:
Leave without notice to anyone.

for Client compilation:
cd C:\\MyData\\Server_Client\\Client
gcc -o client client.c
 copy to the compiled "client.exe" folder the "cygwin1.dll" file
 from "C:\cygwin64\bin" cygwin istalled folder

For the server compilation :
#define USE_SELECT 
//Allow the define above definition will cause to work with socket "select()" function (the old way)
//Undefined above definition will cause to work with socket "poll()" function (instead of "select()")

 run "Cygwin64 Terminal" get the "$" prompt:
  $ cd C:\\MyData\\Server_Client\\Server
  make
  make clean
 copy to the compiled "server.exe" the "cygwin1.dll" file
 from "C:\cygwin64\bin" cygwin istalled folder
 if you complile with another cyggwin e.g. 32 bit cygwin need to use the 32bit "cygwin1.dll"
 mixing 32bit "cygwin1.dll"  with "server.exe" compile 64 bit will crash. 
 with runtime meaasge box display:
 Application Error 
 The application was unable to start correctly(0xc000007b).
 click OK to close the application



