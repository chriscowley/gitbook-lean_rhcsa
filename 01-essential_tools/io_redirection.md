Input/output redirection is the way of controlling where a command's output goes and where it gets input from. 

* STDIN - standard input
  * Could be what the shell sees when you type text on keyboard.
  * Could also be text sent to the command from another command via a _pipe_.
* STDOUT - standard output is where the command sends most of is normal output.
* STDERR - standard error us where the command sends information when something bad happens.


`command > file` is is the simpliest form of redirection. It takes the STDOUT from a command and sends it to file called `file`.

`command < file` tells a command to read the contents of `file` via STDIN

