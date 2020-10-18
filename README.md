# Demon Pentest Shell
A simple shell wrapper for superior logging capabilities. All commands are logged to ```~/log_dps_history.csv``` with with ```When,Host,Network,Who,Where,What```.
This project requires Python3 and the following Python modules,
* prompt_toolkit # for TAB autocompletion of $PATH and built-in commands
* os # for path object
* sys # for exit
* re # regular expressions
* ifaddr # NIC info
* socket # for hostname
* getpass # for username
* datetime # for dates and times
* subprocess # executes cmds by passing them to `/bin/bash`
* configparser # parses dps.ini file

## The Shell
### Autocomplete Feature
![Screenshot of auto-complete text](images/screenshots/dps-autocomplete.PNG)
### Built-In Programming Logic
![foreach() function screenshot](images/screenshots/dps_foreach.png)
## Example Log Output
```
root@demon2:~/Code/dps# cat ~/.log_dps_history.csv 
When,Host,Network,Who,Where,What
2020-04-14 07:56:52.412353,demon2.4,ens33:192.168.159.132,root,/root/Code/dps,ls
2020-04-14 07:56:53.177506,demon2.4,ens33:192.168.159.132,root,/root/Code/dps,cd
2020-04-14 07:56:53.641559,demon2.4,ens33:192.168.159.132,root,/root,ls
2020-04-14 07:56:56.756188,demon2.4,ens33:192.168.159.132,root,/root,cd Penetration Testing
2020-04-14 07:56:58.374275,demon2.4,ens33:192.168.159.132,root,/root/Penetration Testing,ls
2020-04-14 07:57:00.117010,demon2.4,ens33:192.168.159.132,root,/root/Penetration Testing,cd Clients
2020-04-14 07:57:00.389277,demon2.4,ens33:192.168.159.132,root,/root/Penetration Testing/Clients,ls
2020-04-14 07:57:18.294996,demon2.4,ens33:192.168.159.132,root,/root/Penetration Testing/Clients,ifconfig | grep inet
2020-04-14 07:57:31.235330,demon2.4,ens33:192.168.159.132,root,/root/Penetration Testing/Clients,exit
root@demon2:~/Code/dps#
```
## Shiny Features
Because this is built with prompt_toolkit, the shell has a lot of great built-in features. 
* Use pipes for stdout, stderr just like you would in a native shell
### Keyboard Shortcuts
The following keyboard shortcuts are available,
* CTRL+A - move the cursor to the beginning of the line
* CTRL+P - enter the previous command into the temrinal
* CTRL+C - exit the shell gracefully
* CTRL+R - search history
* Up and Down arrows - flip through command history
### Built-In Commands
The following are built-in commands,
* dps_uid_gen - generate a list of UIDs from a CSV file
* dps_wifi_mon - set a Wi-Fi device into monitor mode
* dps_stats - show log stats
* dps_config - set configuration options, such as prompt style
## Installation
To install DPS, simply install the requirements using pip3 and copy the ```dps.py``` into your ```$PATH``` like ```/usr/local/bin```, etc:
```
root@kali:~# cd /tmp
root@kali:/tmp# git clone https://github.com/weaknetlabs/dps.git
root@kali:/tmp# cd dps
root@kali:/tmp/dps# pip3 install -r requirements.txt
root@kali:/tmp/dps# cp dps.py /usr/local/bin/
root@kali:/tmp/dps# dps.py
```
