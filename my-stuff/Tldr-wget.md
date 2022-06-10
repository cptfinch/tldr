A simpler version
wget -qO- http://example.com
equivalent to
wget -q -O - http://example.com
where
	• -q turns off the output of log, including error information
	• -O -, equivlalent to -O /dev/stdout, means dump the web page to a file named /dev/stdout.

From <https://superuser.com/questions/321240/how-do-you-redirect-wget-response-to-standard-out/321241> 



 - Add a remote key to the trusted keystore:
   wget -qO - {{https://host.tld/filename.key}} | apt-key add -








