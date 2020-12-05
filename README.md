# ansible-playbook-linode


An super simple ansible playbook to provision a new linode server,
set its hostname and FQDN,
deploy a public ssh key under its root account,
Enabled password based ssh login (changes /etc/ssh/sshd_config).

Each time you run it, it creates a NEW LINODE SERVER.

### Defaults:

The default configuration (`vars/config.yml`) creates a Linode 1024 in Fremont, CA, USA.
It gives it 1GB swap (it's on SSD) and installs Debian 9.

### Installation

Install the official Python library for the Linode API v4.

        pip install linode_api4

### Usage:

Copy sample config `vars/config.yml.example` to `vars/config.yml`.

Change variables in `vars/config.yml` to suit your needs.

Then,finally deploy instance by running playbook `provision.yml`

```
$ export LINODE_API_KEY="Enter Your API KEY"
$ ansible-playbook provision.yml
```

After the playbook finishes, you can login via ssh as root@THE-IP-IN-THE-OUTPUT.
