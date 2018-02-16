# Unix

#### check for required parameters in a bash script

Easy way to check parameter has been set, and fail with message when missing:

	#!/bin/bash -e
	PARAM=${1?"Usage: $0 <param>"}
	
#### sed: replace over multiple lines

Replaces all new lines with commas

	sed ':a;N;$!ba;s/\n/, /g'
	
#### grep: matching unprintable characters

	grep -P "\x01"

#### awk: specify separator

	awk -F 'abc' {print $1 }
	awk -F '[1-9]+' {print $1 }

#### counting lines

	wc -l
	
#### kill process running on a particular port
	netstat -tlnp 2>&1 | grep <port> | awk -F'[ /]+' '{print $7}' | xargs kill

#### send output to file mid-pipe

	script.sh | tee logfile | other stuff
	
#### send output to terminal mid-pipe

	script.sh | tee /dev/tty | other stuff

#### combine stout and sterr streams

	scriptWithError.sh 2>&1 > out.log
