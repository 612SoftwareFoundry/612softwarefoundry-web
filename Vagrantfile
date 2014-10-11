# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

  config.vm.define "612softwarefoundry-web-v" do |t|
  end

  config.vm.provider :digital_ocean do |provider, override|
    override.ssh.private_key_path = '~/.ssh/id_rsa'
    override.vm.box = 'digital_ocean'
    override.vm.box_url = "https://github.com/smdahlen/vagrant-digitalocean/raw/master/box/digital_ocean.box"

    #provider.name = '612softwarefoundry-web-v'
    provider.token = ENV['DO_TOKEN']
    provider.image = 'Ubuntu 14.04 x64'
    provider.region = 'nyc3'
    provider.size = '1gb'
    provider.backups_enabled = true
    provider.ssh_key_name = ENV['DO_SSH_KEY_NAME']
    provider.setup = true
    config.ssh.username = 'jenna'
  end

  config.vm.provision "file", source: "~/.gitignore_global", destination: "~/.gitignore_global"

  # provisioning with ansible
  config.vm.provision :ansible do |ansible|
    ansible.playbook = "./roles/site.yml"
    #ansible.verbose = "vvv"
  end
end
