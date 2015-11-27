# ansible-playbook-linode

An super simple ansible playbook to provision a new linode server,
set its hostname and FQDN,
deploy a public ssh key under its root account,
disable password based ssh login (changes /etc/ssh/sshd_config).

Each time you run it, it creates a NEW LINODE SERVER.

### Defaults:

The default configuration (`vars/config.yml`) creates a Linode 1024 in Fremont, CA, USA.
It gives it 1GB swap (it's on SSD) and installs Ubuntu 14.04 LTS.

### Usage:

Change variables in `vars/config.yml` to suit your needs.

```
$ export LINODE_API_KEY=4kfjh59shlhdkjhksdj00sdsTTsskklkjoiRPrbDtgHY
$ ansible-playbook --extra-vars server_hostname=hades provision.yml
```

After the playbook finishes, you can login via ssh as root@THE-IP-IN-THE-OUTPUT.
