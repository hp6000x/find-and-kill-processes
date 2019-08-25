# find-and-kill-processes
Scripts to find and kill processes using a search string. Works like pgrep and killall, but works on vaguer search strings!

# psfind

Usage:

	psfind "search string"
  
This will use grep to search the output of "ps aux" to find processes matching the search string.

# pskill

Usage:

	pskill "search string" [ kill options ]
  
This will use psfind to search for processes matching the search string and get the relevant process id, whereupon it will repeatedly issue the kill command once a second until all matching processes are killed. You can put standard options for the kill command (such as -9) after the search string and they will be added when the command is issued. This script will automatically apply sudo to the kill command if the user's $USER does not match the owner of the process.
