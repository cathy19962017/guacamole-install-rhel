# Apache Guacamole Installation Script for RHEL/CentOS
## Introduction
The `guac-install.sh` script is intended to allow easily installing a complete Apache Guacamole server on RHEL/CentOS 7.x and up. The wiki will cover more in-depth what exactly the script includes and how it configures settings. Before using the script read all the documentation and review the script (especially the variables). Test the script in a test environment/server and ensure it functions exactly as desired before attempting to utilize it on a production system.

The Guacamole install script runs an interactive mode that will prompt for a handful of user input. The input allows selecting from a "Stable" version of Guacamole or to build it from git. It installs, by default, the extensions `guacamole-auth-jdbc-mysql-*` and `mysql-connector-java-*` to allow user credentials to be stored in a MariaDB/MySQL database. Nginx is used as the HTTP/Reverse proxy. Additional options within the script allow for connecting to and using LDAP for authentication, securing HTTPS/SSL, installing a custom extension and more. For more information on what options are provided check the wiki.

The goal for the script when complete is to require no further configuration on the server itself for Guacamole to function. This doesn't account for special configurations regarding networking, hardware firewalls, ISP restrictions, etc.

## Requirements to Run the Guacamole Install Script Successfully
- Install RHEL/CentOS minimal 7.x or up (minimal will work as well as other options like Server with GUI).
- `wget` installed.
- The server must have internet access to download the script and files required for installation by the script.
- Sudo or root access on the server.
- If using RHEL, an activated subscription.
- No prior Guacamole installation/configuration (or its major dependant packages like Nginx, Tomcat, MariaDB, etc.).

## "Required" Reading
It is recommended to read/review all the documentation for the script prior to using it including the README and the Wiki, however I highly recommend reading at least the following:

- [Installation Process](https://github.com/Zer0CoolX/guacamole-install-rhel/wiki/Installation-Process,-Prompts-and-Options)
- [Installation Assumptions](https://github.com/Zer0CoolX/guacamole-install-rhel/wiki/Installation-Assumptions)
- [Script Review](https://github.com/Zer0CoolX/guacamole-install-rhel/wiki/Script-Review)

## Downloading and Running the Guacamole Install Script

**WARNING: It is highly recommended to test this script in a dev environment prior to using it in a production setting!**

Download the `guac-install.sh` script from this repo:
```
wget https://raw.githubusercontent.com/Zer0CoolX/guacamole-install-rhel/master/guac-install.sh
```
If installing a custom Guacamole extension, download it as well and take note of its file name and path. See [here](https://github.com/Zer0CoolX/guacamole-install-rhel/wiki/Customizing-the-Apache-Guacamole-Login-Screen) for more details

Make the `guac-install.sh` script executable:
```
chmod +x guac-install.sh
```
Run the script as sudo/root:
```
./guac-install.sh
```
Proceed with the prompts provided by the installer, see wiki for more details.

## Customizing the Apache Guacamole login screen
See this wiki post regarding [Customizing the Apache Guacamole Login Screen](https://github.com/Zer0CoolX/guacamole-install-rhel/wiki/Customizing-the-Apache-Guacamole-Login-Screen) for details on another repo of mine to accomplish this.

## Apache Guacamole install script menus and options example.
This shows all menu options set by a user with the only exception being getting an SSL cert using LetsEncrypt.

![guac-install-menues.gif](https://github.com/Zer0CoolX/guacamole-install-rhel/blob/master/demo-resources/guac-install-menues.gif)

## Script information
I have based this Apache Guacamole install script on multiple other projects with similar goals. There are too many sources to provide credit to.

The script versioning, for now, will be based on the date of the last commit in the format "yyyy_mm_dd".

I have tested this script myself in many different configurations to try and ensure it works in all conditions. Should you find what you think is a bug please report it under the issues section. Even better, if you find a fix for said bug(s) or just have ideas to improve this script please let me know. This script will be something I hope to refine and perfect over time with continued use and help/input from others.

I will be looking to, in the future, add new features/options to the script while also trying to keep it as streamlined as possible. My goal is for this to work in the majority of typical use-cases, not to shape it for unique needs.

Thank you!
