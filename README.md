# Ansible Lab Exercise:

## Pre-requisite
- 1 Linux VM as the remote host
- Network connection to the remote host is allowed

## Exercise
1. Set up your directory with the following directory layout:
```
ansible-project/
├── ansible.cfg
├── inventory.ini
├── playbook.yml
└── roles/
    └── webserver/
        ├── tasks/
        │   └── main.yml
        ├── files/
        │   └── ansible-index.html
        └── templates/
            └── nginx.conf.j2
```

2. Update the file `ansible.cfg` to configure the inventory file location to point to the `inventory.ini` in the created directory.
3. Update the file `inventory.ini` to configure the IP address and private key location to connect to the remote host.
4. Update the file `playbook.yml` to configure the playbook name, remote hosts and specify the role `webserver` to use.
5. Configure the `webserver` role to:
   - Update APT package manager via `apt` module
   - Install Nginx via `apt` module
   - Copy the file `files/ansible-index.html` to the remote host location `/var/www/html/ansible-index.html` using `copy` module
   - Copy the file `templates/nginx.conf` to the remote host location `/etc/nginx/nginx.conf` using `copy module`
   - Start Nginx service via `systemd_service` module
6. Run your playbook with `ansible-playbook` command.
7. Open your browser and access your web server via your remote host IP. 