# Shared Server Environment

Use this file to record the software versions and server settings used by the project.
Update it whenever the shared server is upgraded or when project requirements change.

## Server Summary

| Item | Value |
| --- | --- |
| Project name | Red Crisálida  |
| Server purpose | Web development shared server |
| Hosting provider / location | HostGator/Jacksonville, FL |
| Operating system | AlmaLinux 9.8 |
| Architecture | x86-64 (AMD64) |
| Server timezone | America/New_York |
| Last updated | 2026-07-09 |
| Updated by | Raul Gomez |

## LAMP Stack Versions

| Component | Version | How to check |
| --- | --- | --- |
| Linux / OS release | AlmaLinux 9.8 | `cat /etc/os-release` |
| Apache HTTP Server | Apache/2.4.68 (cPanel) | `httpd -v` |
| MariaDB / MySQL Server | mysql  Ver 14.14 | `mysql --version` |
| PHP CLI | PHP 8.3.32 | `php -v` |
| PHP-FPM | Not accessible | `php-fpm -v` |

## Web Server Details

| Setting | Value | How to check |
| --- | --- | --- |
| Apache service name | `httpd` | `systemctl status httpd` |
| Apache document root | /home2/casamona | `grep -R "DocumentRoot" /etc/httpd/conf /etc/httpd/conf.d` |
| Apache config test | Not accessible | `apachectl configtest` |
| Enabled Apache modules | Not accessible | `httpd -M` |
| Virtual host config path | Not accessible | NA |
| HTTPS enabled | Yes | NA |
| SSL certificate provider | Let's Encrypt | NA |

## PHP Configuration

| Setting | Value | How to check |
| --- | --- | --- |
| Active PHP version | PHP 8.3.32 | `php -v` |
| PHP config file | /opt/cpanel/ea-php83/root/etc/php.ini | `php --ini` |
| PHP Server API | Server API => Command Line Interface | `php -i | grep "Server API"` |
| PHP memory limit | memory_limit => 512M => 512M | `php -i | grep memory_limit` |
| PHP upload max filesize | upload_max_filesize => 512M => 512M | `php -i | grep upload_max_filesize` |
| PHP post max size | post_max_size => 516M => 516M | `php -i | grep post_max_size` |
| PHP max execution time | max_execution_time => 0 => 0 | `php -i | grep max_execution_time` |
| PHP timezone | date.timezone => America/Mexico_City => America/Mexico_City | `php -i | grep "date.timezone"` |

### PHP Extensions

Record required PHP extensions for the project.

| Extension | Installed? | Version / Notes | How to check |
| --- | --- | --- | --- |
| curl | Yes | curl 7.76.1 | `php -m | grep curl` |
| gd | Yes | bundled (2.1.0 compatible)/FreeType Version => 2.10.4 | `php -m | grep gd` |
| intl | Yes | ICU 67.1 | `php -m | grep intl` |
| mbstring | Yes | NA | `php -m | grep mbstring` |
| mysqli | Yes | mysqlnd 8.3.32 | `php -m | grep mysqli` |
| opcache | Yes | PHP 8.3.32 | `php -m | grep Zend OPcache` |
| pdo_mysql | Yes | mysqlnd 8.3.32 | `php -m | grep pdo_mysql` |
| xml | Yes | libxml 2.9.13 | `php -m | grep xml` |
| zip | Yes | Zip 3.0 | `php -m | grep zip` |

## Database Details

| Setting | Value | How to check |
| --- | --- | --- |
| Database server | mysql 5.7.44 | `mysql --version` |
| Database service name |  `mysqld` | `systemctl status mariadb` |
| Database host | `localhost` |  |
| Database port | `3306` |  |
| Default character set | utf8mb3 | `mysql -e "SHOW VARIABLES LIKE 'character_set_server';"` |
| Default collation | utf8_unicode_ci | `mysql -e "SHOW VARIABLES LIKE 'collation_server';"` |

Do not store database passwords in this file.

## Development Tools

| Tool | Version | How to check |
| --- | --- | --- |
| Git | git 2.48.2 | `git --version` |
| Composer | Composer 2.6.5 | `composer --version` |
| Node.js | Not available | `node --version` |
| npm | Not available | `npm --version` |
| Python | python 3.9.25 | `python3 --version` |
| Docker | Not available | `docker --version` |
| Docker Compose | Not available | `docker compose version` |

## Package Sources

| Source | Enabled? | Notes | How to check |
| --- | --- | --- | --- |
| AlmaLinux BaseOS | No |  | `dnf repolist` |
| AlmaLinux AppStream | No |  | `dnf repolist` |
| EPEL | No |  | `dnf repolist | grep epel` |
| Remi PHP repository | No |  | `dnf repolist | grep remi` |

## System Services

| Service | Enabled at boot? | Running? | How to check |
| --- | --- | --- | --- |
| httpd | Yes | Yes | `systemctl is-enabled httpd && systemctl is-active httpd` |
| php-fpm | Yes | Yes | `systemctl is-enabled php-fpm && systemctl is-active php-fpm` |
| mysqld | Yes | Yes | `systemctl is-enabled mariadb && systemctl is-active mariadb` |
| firewalld | Yes | Yes | `systemctl is-enabled firewalld && systemctl is-active firewalld` |
| sshd | Yes | Yes | `systemctl is-enabled sshd && systemctl is-active sshd` |

## Firewall and Ports

| Port / Service | Open? | Purpose | How to check |
| --- | --- | --- | --- |
| 22 / SSH |  | Remote login | `firewall-cmd --list-services` |
| 80 / HTTP |  | Web traffic | `firewall-cmd --list-services` |
| 443 / HTTPS |  | Secure web traffic | `firewall-cmd --list-services` |
| 3306 / MySQL |  | Database access, if needed | `firewall-cmd --list-ports` |

## Project Paths

| Path | Value |
| --- | --- |
| Web root |  |
| Application root |  |
| Logs directory |  |
| Uploads directory |  |
| Backup directory |  |

## Student Access Notes

| Item | Value |
| --- | --- |
| SSH access method |  |
| User account naming convention |  |
| Group used for project files |  |
| File permission policy |  |
| Deployment method |  |

Do not store private keys, passwords, API tokens, or personal credentials in this file.

## Change Log

| Date | Change | Updated by |
| --- | --- | --- |
| YYYY-MM-DD | Initial environment record created. |  |
