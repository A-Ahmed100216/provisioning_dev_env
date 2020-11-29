
Vagrant.configure("2") do |config|

  config.vm.box = "ubuntu/bionic64"
  # Setup private_network
  config.vm.network "private_network",ip: "192.168.10.10"
  # Alias the ip address. 2 ways, both work
  config.vm.hostname="www.development.local"
  config.hostsupdater.aliases=["development.local","project.test"]
  config.vm.provision "file", source: "~/Downloads/starter-code ", destination: "/remote/newfolder"

end
