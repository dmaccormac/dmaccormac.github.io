---
title: FreeBSD config notes
date: 2025-09-02
last_modified_at: 2025-09-02
tags: freebsd unix
excerpt: Just documenting some useful FreeBSD commands.
---


Just documenting some useful FreeBSD commands.


# 1. Adding a user

## Option 1: adduser (interactive)

```bash
adduser
```

This will launch an interactive prompt asking for username, groups, shell, home dir, etc.


## Option 2: Using pw (scriptable)

```bash
pw useradd <username> -m -s /bin/sh -G wheel
```

Then set the password:

```bash
passwd <username>
```

## Option 2: 
# 2. Enable SSH

## 1. Install OpenSSH (if not already installed)

Most FreeBSD installations come with OpenSSH by default. You can check with:

```bash
which sshd
```

If it's not installed, you can install it via:

```bash
pkg install openssh
```


## 2. Enable SSH Service
To start SSH at boot, add this line to /etc/rc.conf:

```bash
sshd_enable="YES"
```

You can do this with:

```bash
sysrc sshd_enable=YES
```

## 3. Start SSH Service
Start the SSH daemon immediately:

```bash
service sshd start

```

## 4. Check Firewall (if applicable)
Ensure port 22 is open if you're using pf or another firewall.

For pf, add to /etc/pf.conf:

```bash
pass in on egress proto tcp from any to any port 22
```

Then reload:

```bash
pfctl -f /etc/pf.conf
```

## 5. Verify SSH is Running
Check status:

```bash
service sshd status
```

Or check listening port:

```bash
sockstat -4 -l | grep ssh
```

