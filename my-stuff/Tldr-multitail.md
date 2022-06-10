
multitail -Q 1 'directory/*' 

-Q 1 PATTERN means to check for new content in existing or new files matching PATTERN every 1 second. Lines from all files are shown in the same window, use -q instead of -Q to have separate windows. 

From <https://unix.stackexchange.com/questions/39729/monitor-files-%C3%A0-la-tail-f-in-an-entire-directory-even-new-ones>  

$ multitail log-file_a log-file_b 

example for two log-files and two columns 

$ multitail -s 2 log-file_a log-file_a 

example for two log-files and different colors 

$ multitail -ci green log-file_a -ci yellow -I log-file_a 

example for one log file on remote 

$ multitail -l "ssh -t <user>@<host> tail -f log-file" 

example for four log files on remote 

$ multitail -l "ssh -l <user> <host> tail -f log-file_a" -l "ssh -l <user> <host> tail -f log-file_b" -l "ssh -l <user>  

From <https://softwaretester.info/monitor-multiple-remote-log-files-with-multitail/>  