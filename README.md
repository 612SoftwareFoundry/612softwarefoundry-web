### 612softwarefoundry-web

This is the vagrant and ansible configuration for a Digital Ocean droplet.

#### Setup

Set variable values in roles/common/vars/main.yml.

Add the following environment variables:

```bash
export DO_TOKEN='the Digital Ocean API token'
export DO_SSH_KEY_NAME='name of the Digital Ocean SSH key to use for setup'
```

Install the provider plugin:

```bash
$ vagrant plugin install vagrant-digitalocean
```

#### Run

```bash
$ vagrant up --provider=digital_ocean
```