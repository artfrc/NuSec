# Linux & System Administration Essentials

## Basic Output Commands
- `echo`: `echo Hello` - print Hello
- `whoami`: print the current user
- `pwd`: print working directory

## File and Directory Navigation
- `ls`: list all files in the current directory
- `cd`: change directory

## File Content Operations
- `cat`: concatenate (print content of file)
- `grep`: search contents of files for specific values  
  Example: `grep "some text" filename`

## File Search
- `find`:  
  `find -name filename.txt`: search for `filename.txt` recursively

## File Analysis
- `wc`: count the number of entries

## File System Interaction
- `touch`: create a new empty file
- `mkdir`: create a new directory
- `cp`: copy files or directories
- `mv`: move or rename files or directories
- `rm`: remove files or directories
- `file`: determine the type of a file

## Operators
- `&`: run commands in the background
- `&&`: combine multiple commands in one line
- `>`: redirect output
- `>>`: append output instead of replacing

## Secure Shell (SSH)
- `ssh`: Secure communication via encryption  
  Example: `ssh {user}@{IP}`

## Permissions
- `ll` or `ls -l`: list files with detailed permissions
- `su {user}`: switch to another user account

## Common Directories
- `/etc`: contains system files and configurations (e.g., `sudoers`, `passwd`)
- `/var`: contains frequently accessed or written data (e.g., logs, databases)
- `/tmp`: temporary directory cleared on reboot, writable by all users

## Downloading Files - `wget`
Example:  
`wget https://assets.tryhackme.com/additional/linux-fundamentals/part3/myfile.txt`

## File Transfer via SCP
Secure copy using SSH protocol.

**Copy to Remote System:**
```bash
scp important.txt ubuntu@192.168.1.30:/home/ubuntu/transferred.txt
```

**Copy from Remote System:**
```bash
scp ubuntu@192.168.1.30:/home/ubuntu/documents.txt notes.txt
```

## Serving Files From Your Host - Python HTTP Server
```bash
python3 -m http.server
```
Download file from another machine:  
```bash
wget http://MACHINE_IP:8000/myfile
```

## Process Management
- `ps`: view user processes
- `ps aux`: view all processes
- `top`: real-time process stats
- `kill <PID>`: kill a process

### Common Signals
- `SIGTERM`: graceful termination
- `SIGKILL`: forceful kill
- `SIGSTOP`: suspend process

## Starting Services on Boot - `systemctl`
```bash
systemctl start apache
systemctl stop apache
systemctl enable apache
systemctl disable apache
```

## Automation with Crontabs
A crontab has six fields:
- MIN
- HOUR
- DOM (Day of Month)
- MON (Month)
- DOW (Day of Week)
- CMD (Command)

**Example:**
```bash
0 */12 * * * cp -R /home/cmnatic/Documents /var/backups/
```

Edit crontab:  
`crontab -e`

## Managing Repositories (APT)
### Add Repository
```bash
wget -qO - https://download.sublimetext.com/sublimehq-pub.gpg | sudo apt-key add -
touch /etc/apt/sources.list.d/sublime-text.list
# Add: deb https://download.sublimetext.com
sudo apt update
sudo apt install sublime-text
```

### Remove Repository
```bash
sudo add-apt-repository --remove ppa:PPA_Name/ppa
sudo apt remove sublime-text
```

## System Logs
Common services and their logs:
- Apache2: access and error logs
- fail2ban: brute force monitoring
- UFW: firewall logs

Logs help diagnose issues and investigate suspicious activity.
