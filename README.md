# Ansible Playbook to launch a DigitalOcean droplet

This playbook does the following:
- Creates a DigitalOcean droplet
- Adds the droplet's IP address to the [ansible inventory file](hosts) under the name do_droplets
- Setup the swap file
- Installs and setup fail2ban
- Setup the firewall
- Setup the timezone
- Adds a new user account with sudo access
- Adds a public ssh key for the new user account
- Disables password authentication to the droplet
- Deny root login to the droplet
- Installs the UnattendedUpgrades package for automatic security updates

## Usage

- Modify the values in `group_vars/all/main.yml.example` and `group_vars/all/secret.yml.example`.
- Rename the `group_vars/all/secret.yml.example` file to `group_vars/all/secret.yml` and `group_vars/all/main.yml.example` file to `group_vars/all/main.yml`.
- Run the following:
```
ansible-galaxy install -r requirements.yml
ansible-playbook -i hosts main.yml
```
