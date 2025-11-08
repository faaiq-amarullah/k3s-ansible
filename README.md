1. Install Ansible \
Check out this reference: [Installing Ansible on specific operating systems](https://docs.ansible.com/ansible/latest/installation_guide/installation_distros.html)
```
sudo apt update
sudo apt install software-properties-common
sudo add-apt-repository --yes --update ppa:ansible/ansible
sudo apt install ansible
```

2. Clone Ansible Repository
```
git clone https://github.com/faaiq-amarullah/k3s-ansible.git
cd ansible
```

3. Configure inventory.yml \
You can check the inventory.yaml file for a configuration example. Please note that if you are running a load balancer on the master node, make sure that the `haproxy_listen_port` and `https-listen-port` ports do not conflict.

4. Running the playbook \
```
# Provision
ansible-playbook playbooks/site.yml -i inventory.yml

# Upgrade
ansible-playbook playbooks/upgrade.yml -i inventory.yml

# Destroy
ansible-playbook playbooks/reset.yml -i inventory.yml

# Reboot
ansible-playbook playbooks/reboot.yml -i inventory.yml
```

