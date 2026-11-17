# Shell Cheat Sheet 
|Command|Function|FDE-use|
|---|---|---|
|pwd|where am I|
|echo| print|
|cd| change directory| to get into a new folder|
|cd.| know where you are|
|cd..| parent directory| one level up
|cd ~| back to home|
|man| to know what all is there in shell|
|ls|list the directories there|
|Ctrl+C|Cancels or kills whatever is running
|ls -l / ls -lh|Detailed list (permissions, size); -h shows sizes as KB/MB/GB
|echo $PATH	|Shows the list of folders the shell searches for programs
|cat	|Prints a whole file
|head / head -n 5|First 10 lines, or the first n
|tail / tail -n 5|Last 10 lines, or the last n
|sort|Sorts lines alphabetically, so 3, 31, 4 comes out in that order
|grep pattern file|Prints lines inside a file that match the pattern	
|grep -r|Searches every file in all subfolders
|grep -l|Prints only the names of files that match
|uniq| Removes duplicates, but only when they’re next to each other, so sort first
|uniq -c	Same, |plus a count of each line
|chmod +x lecture.sh|Make the file executable
