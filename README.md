RCAT-Mail-System
====================

This is the public repository for [RCAT-Mail-System].

RCAT Mail System is a yum based solution for mail system installation.

RCAT Mail System can be installed by one-key installation script, all configuration will be setup automatically including the SSL/TLS and STARTTLS support for SMTPs/IMAPs/POP3s.

RCAT has a simple management panel to manage your mail server, therefore you can create account, delete account, and modify password easily.

After creating account, you can connect to your mail server via any mail client.

Environment:
- VPS/Dedicated server which support rdns
- Centos 6
- Iptables
- Wget 1.12 or newer
- Postfix (will be installed)
- Dovecot (will be installed)
- Postgrey (will be installed)
- rpmforge-release (will be installed)
- epel-release (will be installed)
- postfix-policyd-spf-perl (will be installed)
- server.crt, server.key

Note:
- This system will be updated with advanced configuration like anti-spam if I have free time. XD

Installation
-------
### basic installation
    yum update wget -y;
    wget -O rcat_mail_system https://raw.githubusercontent.com/gidcs/RCAT-Mail-System/master/rcat_mail_system;
    chmod 755 rcat_mail_system;
    ./rcat_mail_system 2>&1 | tee rcat_mail_system.log

### quick installation
    yum update wget -y;
    wget -O rcat_mail_system https://raw.githubusercontent.com/gidcs/RCAT-Mail-System/master/rcat_mail_system;
    chmod 755 rcat_mail_system;
    ./rcat_mail_system -i {hostname} {default_domain} 2>&1 | tee rcat_mail_system.log

Help Information
-------
### quick installation
    rcat_mail_system -i {hostname} {default_domain}

### quick adding account
    rcat_mail_system -a {username} {password}

### quick modifying password
    rcat_mail_system -m {username} {password}

### quick deleting account
    rcat_mail_system -d {username}

License
-------

Copyright 2015 [guyusoftware]

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

    http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.

[guyusoftware]: https://www.guyusoftware.com/
[RCAT-Mail-System]: http://rcat.gidcs.net/rcat-mail-system

Log
-------

### 2016-02-13
    RCAT-Mail-System(Postfix+Dovecot) release.

### 2016-02-14
    Real-time Blackhole List (RBL) and Postgrey is added.
    Policy engine SPF checking postfix-policyd-spf-perl is added.
    Spamassassin is added.
