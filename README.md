----
# ansible-role-app-fail2ban
Install and configure [fail2ban](https://www.fail2ban.org/wiki/index.php/Main_Page) on Ubuntu and RedHat based distros

## Jails
A standard SSH jail with a 10 minute lockout after 3 failed attempts

## Default variables
| Name | Type | Value | Purpose |
| ---- | ---- | ----- | ------- |
| fail2ban_ignoreip      | string  | "" | DEPRECATED Space separated list of IPs to never ban |
| fail2ban_ignore_addrs  | list(IpV4) | [] | list of addresses to never ban |
| fail2ban_pkgs          | list    | ['fail2ban'] | which packages to install |
| fail2ban_refresh_cache | Boolean | true         | whether to refresh package cache before install |
| fail2ban_state         | string  | present      | set to absent to remove the package |
| fail2ban_svc_enabled   | Boolean | true         | if true, the service will start at boot |
| fail2ban_svc_name      | string  | fail2ban     | name of the service |
| fail2ban_svc_state     | string  | started      | what state to have the service in |

## Dependencies
On Amazon Linux2, requires EPEL to find fail2ban
```
amazon-linux-extras install epel -y
```

## Supported distros
Tested on Amazon Linux 2
Tested on Ubuntu 18,20,22 and should work on any modern Debian distribution
****
