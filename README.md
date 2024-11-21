# Useful linux commands for the cyber security

## Enumeration
### System Information
- `hostname`
- `uname -a`
- `cat /proc/version`
- `cat /etc/issue`

### Process Information
- `ps`
- `ps -A`
- `ps axjf`
- `ps aux`

### Environment Information
- `env`

### Sudo Privileges
- `sudo -l`

### File and Directory Information
- `ls`
- `ls -la`

### User and Privilege Information
- `id`
- `cat /etc/passwd`

### Command History
- `history`

### Network Information
- `ifconfig`
- `ip route`
- `netstat`
  - `netstat -a`
  - `netstat -at`
  - `netstat -au`
  - `netstat -l`
  - `netstat -s`
  - `netstat -tp`
  - `netstat -ano`
  - `netstat -i`

### File Search
- `find . -name <filename>`
- `find /home -name <filename>`
- `find / -type d -name <directory_name>`
- `find / -type f -perm 0777`
- `find / -perm a=x`
- `find /home -user <username>`
- `find / -mtime <days>`
- `find / -atime <days>`
- `find / -cmin -<minutes>`
- `find / -amin -<minutes>`
- `find / -size <size>`
- `find / -size +<size>`
- `find / -size -<size>`
