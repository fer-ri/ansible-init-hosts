# Ansible Init

Setup fresh server(s) to make it ready for Ansible.

It generates SSH Keys on local if not exists, copies to host, and install Python3.

## Install Ansible

```bash
apt-add-repository --yes --update ppa:ansible/ansible
apt install ansible
ansible --version
```

## Init

Run this command for single server

```bash
ansible-playbook -i some-host:host-port, --ask-pass init.yml
```

Enter server password when prompted.

> Note: A `,` (comma) after host/port is required

To init multiple servers then please setup the `hosts` (renamed from hosts.example) file in the following format

```ini
some-host-1:port ansible_password=host_root_password
some-host-2:port ansible_password=host_root_password
```

Then run this command

```bash
ansible-playbook init.yml
```

---

Inspired by [prepare-ansible-hosts](https://github.com/jonsbun/ansible-init/) and [ansible-init](https://github.com/pachico/prepare-ansible-hosts)