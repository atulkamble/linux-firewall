**Linux firewall management commands** for popular firewall tools: **iptables**, **firewalld**, and **ufw**.

---

## 📖 Linux Firewall Commands

---

## 🔥 `iptables` Commands

*(Legacy but still widely found on older systems)*

| Action              | Command Example                                      |
| :------------------ | :--------------------------------------------------- |
| View current rules  | `sudo iptables -L -v -n`                             |
| Allow inbound port  | `sudo iptables -A INPUT -p tcp --dport 80 -j ACCEPT` |
| Block an IP         | `sudo iptables -A INPUT -s 192.168.1.100 -j DROP`    |
| Delete a rule       | `sudo iptables -D INPUT -p tcp --dport 80 -j ACCEPT` |
| Save rules (Debian) | `sudo iptables-save > /etc/iptables/rules.v4`        |
| Save rules (RHEL)   | `sudo service iptables save`                         |
| Flush all rules     | `sudo iptables -F`                                   |

---

## 🔥 `firewalld` Commands

*(Modern default on RHEL, CentOS 7+, Fedora, Rocky Linux, AlmaLinux)*

| Action                    | Command Example                                                                                            |      |                    |
| :------------------------ | :--------------------------------------------------------------------------------------------------------- | ---- | ------------------ |
| Check status              | `sudo firewall-cmd --state`                                                                                |      |                    |
| List all active rules     | `sudo firewall-cmd --list-all`                                                                             |      |                    |
| Start/Stop/Enable service | \`sudo systemctl start                                                                                     | stop | enable firewalld\` |
| Open a port (permanent)   | `sudo firewall-cmd --permanent --add-port=80/tcp`                                                          |      |                    |
| Remove a port (permanent) | `sudo firewall-cmd --permanent --remove-port=80/tcp`                                                       |      |                    |
| Reload to apply changes   | `sudo firewall-cmd --reload`                                                                               |      |                    |
| Allow service (e.g. HTTP) | `sudo firewall-cmd --permanent --add-service=http`                                                         |      |                    |
| Block IP address          | `sudo firewall-cmd --permanent --add-rich-rule='rule family="ipv4" source address="192.168.1.100" reject'` |      |                    |
| List zones                | `sudo firewall-cmd --get-zones`                                                                            |      |                    |

---

## 🔥 `ufw` (Uncomplicated Firewall) Commands

*(Ubuntu and derivatives)*

| Action           | Command Example                    |
| :--------------- | :--------------------------------- |
| Check status     | `sudo ufw status`                  |
| Enable UFW       | `sudo ufw enable`                  |
| Disable UFW      | `sudo ufw disable`                 |
| Allow port       | `sudo ufw allow 22`                |
| Deny port        | `sudo ufw deny 22`                 |
| Allow service    | `sudo ufw allow http`              |
| Block IP address | `sudo ufw deny from 192.168.1.100` |
| Delete a rule    | `sudo ufw delete allow 22`         |
| Reset firewall   | `sudo ufw reset`                   |

---

## 📌 Quick Notes:

* **firewalld** uses **zones** to manage different network areas.
* **iptables** is rule-based, order matters.
* **ufw** is a simplified wrapper for iptables on Ubuntu.
* After modifying firewall settings, always test connectivity.

## 👨‍💻 Author

**Atul Kamble**

- 💼 [LinkedIn](https://www.linkedin.com/in/atuljkamble)
- 🐙 [GitHub](https://github.com/atulkamble)
- 🐦 [X](https://x.com/Atul_Kamble)
- 📷 [Instagram](https://www.instagram.com/atuljkamble)
- 🌐 [Website](https://www.atulkamble.in)

