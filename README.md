# 
<h1 align="center">Welcome to Setting Up WAGATIL CMS USING UWSGI and NGINX 👋</h1>
<p align="center">
  <img src="https://img.shields.io/badge/ANSIBLE-EE0000?labelColor=EE0000&color=grey&logo=Ansible&style=social%22" />
  <img src="https://img.shields.io/badge/PYTHON-3776AB?labelColor=ffffff&color=grey&logo=Python&style=social%22" />
  <img src="https://img.shields.io/badge/DJANGO-3776AB?labelColor=092E20&color=grey&logo=Django&style=social%22" />
  <img src="https://img.shields.io/badge/NGINX-269539?labelColor=ffffff&color=grey&logo=NGINX&style=social%2" />
  </br>
  <a href="https://twitter.com/mfaisaltariq01" target="_blank">
    <img alt="Twitter: mfaisaltariq01" src="https://img.shields.io/twitter/follow/mfaisaltariq01.svg?style=social" />
  </a>
</p>

------

This repository will will configure and setup a demo Wagtail CMS that is served using **uwsgi** and proxied through **nginx**.

## NOTE
------------
All the roles have been test with **CentOS7**.

The Role for **mariadb** have been reused from the **bertv.mariadb** ansible-galaxy official repository

## ROLES
------------
> MARIADB

- The maria db role installs mariadb from the official repository </br>
- Remove all the test dbs/users </br>
- Creates our custom user and database and assign all priviledges of the database to our custom user

> WAGTAIL

- The wagtail role installs python3, pip, wagtail, uwsgi and other dependencies </br>
- Sets up a virtual python environments </br>
- Creates a wagtail project and configures it to us mariadb instead of SQLite </br>
- Configures the project with uwsgi. </br>
- Starts uwsgi service to serve pages to the user </br>

> NGINX

- The nginx role installs nginx and enables service on startup </br>
- Configures environment to proxy uwsgi </br>
- Disable selinux so that nginx can run without any permissions issue </br>
**This can be improved by setting selinux to permissive mode instead of completly disabling it**

## Usage
--------------

- Add the host to the inventory file </br>
- In the **host_vars** directory create a new file. Name of the file should be the hostname/IP of the managed host and set the variables accordingly. (See the sample **host_vars/localhost** file). </br>
- Run the **ansible-playbook e2e-setup.yaml** playbook to simulate the end 2 end senario of setting up the entire environment.

> **NOTE:** </br>
A restart of the server might be required after the setup to make sure selinux policies take effect.

## Author

👤 **Muhammad Faisal Tariq**

<p>
  <a href="https://twitter.com/mfaisaltariq01" target="_blank">
    <img alt="Twitter: mfaisaltariq01" src="https://img.shields.io/badge/Twitter%20%20%20-Follow-13324B?logoWidth=24&labelColor=13324B&color=grey&logo=Twitter&style=social%22" />
  </a>
  </br>
  <a href="https://github.com/mfaisaltariq" target="_blank">
    <img alt="Github: mfaisaltariq" src="https://img.shields.io/badge/GitHub-Follow-181717?logoWidth=24&labelColor=181717&color=grey&logo=GitHub&style=social%22" />
  </a>
  </br>
  <a href="https://linkedin.com/in/mfaisaltariq" target="_blank">
    <img alt="LinkedIn: mfaisaltariq" src="https://img.shields.io/badge/LinkedIn-Follow-0077b5?labelColor=0077b5&color=grey&logo=LinkedIn&style=social%22" />
  </a>
  </br>
  <a href="https://www.youtube.com/c/DesktopDev_mfaisaltariq" target="_blank">
    <img alt="YouTube: mfaisaltariq" src="https://img.shields.io/badge/YouTube-Subscribe-FF0000?labelColor=FF0000&color=grey&logo=YouTube&style=social%22" />
  </a>
</p>

## Show your support

Give a ⭐️ if this project helped you!


