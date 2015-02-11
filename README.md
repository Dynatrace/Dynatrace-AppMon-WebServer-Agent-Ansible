# Dynatrace-WebServer-Agent-Ansible

An [Ansible](http://www.ansible.com) role for automated deployments of the [Dynatrace](http://bit.ly/dttrial) WebServer Agent.

**Note**: This role merely installs the Web Server Agent - it will not configure your web server to actually include it.

**Note**: Currently, we support only Linux hosts, support for installing Windows hosts is in the making.

## Download

The role is available via:

- [Ansible Galaxy](https://galaxy.ansible.com/list#/roles/2625)
- [GitHub](https://github.com/Dynatrace/Dynatrace-WebServer-Agent-Ansible)

## Requirements

Download the Dynatrace Web Server Agent installer from [downloads.compuwareapm.com](http://downloads.compuwareapm.com) and place the artifact as ```dynatrace-wsagent.tar``` in the role's ```files``` directory from where it will be picked up during the automated installation.

## Role Variables

As defined in ```defaults/main.yml```:

| Name                                          | Default | Description |
|-----------------------------------------------|---------------------------|-------------|
| *dynatrace_wsagent_linux_install_dir*         | /opt                      | The Dynatrace Web Server Agent will be installed into the directory *$dynatrace_wsagent_linux_install_dir*/dynatrace-*$major*-*$minor*-*$rev*, where *$major*, *$minor* and *$rev* are given by the installer. A symbolic link to the actual installation directory will be created in *$dynatrace_wsagent_linux_install_dir*/dynatrace. |
| *dynatrace_wsagent_linux_installer_file_name* | dynatrace-wsagent.tar     | The file name of the Dynatrace Web Server Agent installer in the role's ```files``` directory. |
| *dynatrace_wsagent_name*                      | dtwsagent                 | The name the Web Server Agent as it appears in Dynatrace. |
| *dynatrace_wsagent_collector_hostname*        | localhost                 | The location of the Collector the Web Server Agent shall connect to. |
| *dynatrace_wsagent_collector_port*            | 9998                      | The port on the Collector the Web Server Agent shall connect to. |
| *dynatrace_wsagent_role_name*                 | Dynatrace-WebServer-Agent | The actual name of this role in an [Ansible Playbook's](http://docs.ansible.com/playbooks.html) ```roles``` directory. |

## Example Playbook

	- hosts: all
	  roles:
	    - { role: Dynatrace-WebServer-Agent }

## Additional Resources

- [Slide Deck: Automated Deployments](http://slideshare.net/MartinEtmajer/automated-deployments-slide-share)
- [Slide Deck: Introduction to Automated Deployments with Ansible](http://www.slideshare.net/MartinEtmajer/introduction-to-automated-deployments-with-ansible)

## Questions?

Feel free to post your questions on the Dynatrace Community's [Continuous Delivery Forum](https://community.dynatrace.com/community/pages/viewpage.action?pageId=46628921).

## License

Licensed under the MIT License. See the LICENSE file for details.
