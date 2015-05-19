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

| Name                                          | Default                                          | Description |
|-----------------------------------------------|--------------------------------------------------|-------------|
| *dynatrace_wsagent_linux_install_dir*         | /opt                                             | The Dynatrace Web Server Agent will be installed into the directory *$dynatrace_wsagent_linux_install_dir*/dynatrace-*$major*-*$minor*-*$rev*, where *$major*, *$minor* and *$rev* are given by the installer. A symbolic link to the actual installation directory will be created in *$dynatrace_wsagent_linux_install_dir*/dynatrace. |
| *dynatrace_wsagent_linux_installer_file_name* | dynatrace-wsagent.tar                            | The file name of the Dynatrace Web Server Agent installer in the role's ```files``` directory. |
| *dynatrace_wsagent_linux_installer_file_url*  | http://localhost/dynatrace/dynatrace-wsagent.tar | A HTTP, HTTPS or FTP URL to the Dynatrace Web Server Agent installer in the form (http\|https\|ftp)://[user[:pass]]@host.domain[:port]/path. |
| *dynatrace_wsagent_name*                      | dtwsagent                                        | The name the Web Server Agent as it appears in Dynatrace. |
| *dynatrace_wsagent_collector_hostname*        | localhost                                        | The location of the Collector the Web Server Agent shall connect to. |
| *dynatrace_wsagent_collector_port*            | 9998                                             | The port on the Collector the Web Server Agent shall connect to. |
| *dynatrace_wsagent_role_name*                 | dynatrace.Dynatrace-WebServer-Agent              | The actual name of this role in an [Ansible Playbook's](http://docs.ansible.com/playbooks.html) ```roles``` directory. |

## Example Playbook

	- hosts: all
	  roles:
	    - role: dynatrace.Dynatrace-WebServer-Agent

## Additional Resources

- [Blog: How to Automate Enterprise Application Monitoring with Ansible](http://apmblog.dynatrace.com/2015/03/04/how-to-automate-enterprise-application-monitoring-with-ansible/)
- [Blog: How to Automate Enterprise Application Monitoring with Ansible - Part II](http://apmblog.dynatrace.com/2015/04/23/how-to-automate-enterprise-application-monitoring-with-ansible-part-ii/)
- [Slide Deck: Automated Deployments](http://slideshare.net/MartinEtmajer/automated-deployments-slide-share)
- [Slide Deck: Automated Deployments (of Dynatrace) with Ansible](http://www.slideshare.net/MartinEtmajer/automated-deployments-with-ansible)
- [Slide Deck: Testing Ansible Roles with Test Kitchen, Serverspec and RSpec](http://www.slideshare.net/MartinEtmajer/testing-ansible-roles-with-test-kitchen-serverspec-and-rspec-48185017)
- [Tutorials: Automated Deployments (of Dynatrace) with Ansible](https://community.compuwareapm.com/community/display/COE/Tutorials+on+Automated+Deployments#TutorialsonAutomatedDeployments-ansible)

## Questions?

Feel free to post your questions on the Dynatrace Community's [Continuous Delivery Forum](https://community.dynatrace.com/community/pages/viewpage.action?pageId=46628921).

## License

Licensed under the MIT License. See the LICENSE file for details.
[![analytics](https://www.google-analytics.com/collect?v=1&t=pageview&_s=1&dl=https%3A%2F%2Fgithub.com%2FdynaTrace&dp=%2FDynatrace-WebServer-Agent-Ansible&dt=Dynatrace-WebServer-Agent-Ansible&_u=Dynatrace~&cid=github.com%2FdynaTrace&tid=UA-54510554-5&aip=1)]()
