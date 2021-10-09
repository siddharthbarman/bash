# Bash keystrokes
```
CTRL + A 			                    Move to beginning of line
CTRL + E			                     Move to end of line
CTRL + <- 			                   Back one word
CTRL + ->			                    Forward one word
CTRL + U			                     Cuts text from cursor to start of line	
CTRL + K			                     Cuts text from cursor to end of line		
CTRL + Y			                     Paste cropped text
CTRL + SHF + C		                Copy to clipboard
CTRL + SHF + V		                Paste
CTRL + R			                     Search typed commands
CTRL + C			                     Cancel current command
UP 					                        Previous command
DOWN				                        Next command
TAB					                        File system object name completion
```
# Bash commands
```bash
apropos "<string>"				          Lists command which have anything to do with the string
echo "text"						               Print text on screen and append a newline at the end
echo -n "text"					             Print text on screen without appending newline
file <filepath>					            Print the type of file
stat <filepath>					            Print information about the file
whoami							                   Print the logged in user's name
cd								                      Without any parameters takes you to your home directory
cd My\ Folder					              Same as cd "My Folder"
env | less						                Print environment variables and paginate the results
ls -lh							                   Print the size with units like K (KB), M (MB).
ls -a ~/						                  List all files in my home directory (shows .profile file) 
mkdir folder1 folder2 			       Create the specified folders
mkdir -p f1/f2/f3				           Create all the folders including parents, child
rm -rf <folder path>			         Delete the folder and everything it in
find <path> -name <pattern>		   Look for files & folders with name matching the pattern
sudo useradd <user>				         Create a user without a home directory
sudo useradd -m <user> -c <FN> 	Create a user with a home directory (-m) and fullname 
sudo passwd <user>				          Sets a password for the specified user
su <user>						                 Switch user to specified user
sudo <command>					             Run the command as root e.g. sudo ls /root
sudo -k							                  Relinquish root privileges
sudo -s							                  Switch to root user
exit							                     Exit from being root user, exit the current shell
chmod 777 <filepath>			         All permissions to everyone
chmod a+rwx <filepath>			       All permissions to everyone
chmod 755 <filepath>			         All permissions for me, read & exec for group and others
chmod u+rwx,g=rx,o=rx			        All permissions for me, read & exec for group and others
chmod a-x						                 Remove execute permission from everyone
chown <user> <filepath>			      Make <user> the owner of the file
ls -s <source> <destination>	   Create a soft link
ln <source> <destination>		     Create a hard link
echo "hello world" | wc			      Print the number of lines, words & characters
cat <filepath>					             Print the contents of a file on stdout
cat -n <filepath>				           Print the contents of a file and show line numbers
head <filepath>					            Print the first 10 lines of a file
tail <filepath>					            Print the last 10 lines of a file
head -n3 <filepath>				         Print the first 3 lines of a file
tail -n2 <filepath>				         Print the last 2 lines of a file
cat -n <filepath> | tail -n5	   Print the last 5 lines of a file along with line numbers
less <filepath>					            Print a file & use UP/DOWN/ENTER for navigation 
grep -i "text" <file>			        Print lines containing the text (case-insensitive)
grep -n "text" <file>			        Print lines containing the text with line numbers
grep -v "text" <file>			        Print lines which do not contain the text
grep '\bs[a-z]*e\b' <file>		    Print lines having word start with s & end with e
grep 'hello\|world' <file>		    Print lines having words 'hello' or 'world' 
awk '{print $2}' <file>			      Print the 2nd column of a TSV file
awk '{print $1 " "  $2}' <file> Prints the 1st and 2nd columns and sorts the output
| sort -n
sort -k2 -n <file>				          Perform numerical sort based on 2nd column & print		
sed "s/abc/xyz/" <file>			      Replaces occurences of 'abc' with 'xyz'
tar cvf <file.tar> *.txt		      Create tar file of all txt files in the current folder	tar cavf <file.tar> *.txt		Create compressed tar file			
tar xf <file.tar.gz>			         Extract the tar in current directory
tar xf <file.tar.gz> -C <path>  Extract the tar in a specific directory
zip -r <file.zip> <path>		      Zip all files in <path>
unzip <file.zip>				            Unzips to current directory
unzip <file.zip> -d <path>		    Unzips to a specific directory
command 1 > <file>				          Redirect output (1=stdout) of command to a file
command > <file>				            Redirect output of command to a file
echo -n "hello" > greet.txt		   Write 'hello' into file greet.txt overwriting all content
echo ", World" >> greet.txt		   Append ', World' to file greet.txt
which <program-name>			         Find location where program exists e.g. which bash

```

# File permissions



| Item   | Read (4) | Write (2) | Execute (1) | Result      |
| ------ | -------- | --------- | ----------- | ----------- |
| User   | r        | w         | x           | *7* (4+2+1) |
| Group  | r        | -         | x           | 5 (4+1)     |
| Others | r        | -         | -           | 4 (4)       |

File system

```
/			root directory
 - home		 stores user home folders
 - root		 root's home folder
 - etc		  configuration for various programs
 - bin		  contains binaries
 - sbin		 container binaries
 - lib		  shared libraries and modules
 - dev		  devices attached to the computer
 - mnt		  mounted file systems
 - media		removable file system like USB drives
 - proc		 virtual folder containing processes
 - sys		  virtual folder containing kernel values
```

# VI Commands

```
ESC			                Command mode
i			                  Insert at cursor position
SHF + i		             Insert at beginning of file
a			                  Append at cursor position
SHF + a		             Append at end of line
SHF + g		             Go to end of file
1 + SHF + G           Go to beginning of file
(			                  Move one sentence back
)			                  Move one sentence forward
{			                  Move one paragraph back
}			                  Move one paragraph forward
dd			                 Delete line
/			                  Search text 
?			                  Search text backward
:w			                 Save file
:w <file>	            Save the file as 
:q			                 Quit Vi
:q!			                Quit without saving
:wq			                Save and quit Vi
```
