require 'json'
require 'yaml'

if File.exists? "settings.yml" then
  settings = YAML::load(File.read("settings.yml"))
elsif File.exists? "settings.json" then
  settings = JSON.parse(File.read("settings.json"))
else
  abort("No settings file provided")
end

Vagrant.configure(2) do |config|
  config.vm.box = "ubuntu/trusty64"
  config.vm.hostname = "datascience"

  config.ssh.forward_agent = true
  config.vm.network "forwarded_port", guest: 8080, host: settings["port"]
  config.vm.network "private_network", ip: settings["ip"]

  config.vm.synced_folder settings["notebooks"], "/notebooks"

  config.vm.provider "virtualbox" do |vb|
    vb.name = settings["name"]
    vb.memory = settings["memory"]
    vb.cpus = settings["cpus"]
  end

  config.vm.provision "ansible" do |ansible|
      ansible.playbook = "provision/main.yml"
    end
end

