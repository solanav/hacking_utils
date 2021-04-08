# Reconnaissance
## NMAP
* Create the nmap folder to save results
```bash
$ mkdir nmap
```

* Scan with default scripts, version checking, all formats
```bash
$ sudo nmap -sC -sV -oA nmap/$PROJECT_NAME $IP  
```

* Scan all ports, all formats
```bash
$ sudo nmap -p- $IP -oA nmap/$PROJECT_NAME
```

# Fuzzing
## ffuf - Fuzzing API endpoints
* Fuzz with a random dictionary to find new endpoints
```bash
$ ffuf -u http://$ADDRESS/FUZZ -w $DICTIONARY 
```

* You can also fuzz with a dictionary of special characters to check if something breaks the API

* If the API responds with a certain HTTP code (ex. 500 or 404) you can include it in ffuf output.
```bash
$ ffuf -u http://$ADDRESS/FUZZ -w $DICTIONARY -mc 200,500,404
```

* You can filter responses with a certain number of words
```bash
$ ffuf -u http://$ADDRESS/FUZZ -w $DICTIONARY -fw 5
```

## gobuster - Fuzzing API endpoints
```bash

```

# Exploiting
## Metasploit
* Start metasploit

```bash
$ sudo msfdb run
```

* Search inside metasploit
```bash
msf6 > search $APP_NAME 
```

* Select exploit
```bash
msf6 > use $EXPLOIT_NUMBER
```

* Show options of exploit
```bash
msf6 > show options
```

* Show targets of exploit (versions and all that)
```bash
msf6 > show targets
```

* Set options
```bash
msf6 > set $OPTION $VALUE
```

* Set the payload you want to install
```bash
msf6 > show payloads
msf6 > set payload $VALUE
```

* Run exploit
```bash
msf6 > run
```

# Post-exploitation
## NetCat
* Basic listening for reverse shells
```bash
$ nc -lvnp $PORT
```

## Stealing SSH private key
* If you get an id_rsa file (OpenSSH private key) you can do the following to use it:
```bash
$ echo $PRIVATE_KEY > keyfile
$ chmod 600 keyfile
$ ssh -i keyfile $USER@$IP
```