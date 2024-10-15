# Awk- sed 
To extract and manipulate information from the /etc/passwd file in Linux using awk and sed, you can efficiently parse user information like usernames, home directories, and user IDs.

The /etc/passwd file contains user account information in a colon-separated format:

username:x:UID:GID:comment:home_directory:shell

Using awk:

You can use awk to print specific fields from the /etc/passwd file. For example:

To print usernames and their home directories:

awk -F: '{print $1, $6}' /etc/passwd

Here, $1 is the username, and $6 is the home directory.

To list all users with UID greater than 1000 (non-system users):

awk -F: '$3 > 1000 {print $1, $3}' /etc/passwd


Using sed:

You can use sed to modify or extract specific parts of the /etc/passwd file:

To replace the shell for all users who have /bin/bash with /bin/zsh:

sed 's/\/bin\/bash/\/bin\/zsh/' /etc/passwd

To display only the usernames (first field):

sed 's/:.*//' /etc/

