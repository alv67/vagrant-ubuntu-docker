Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/focal64"
  # --- Port Forwarding ---
  # Node-RED
  config.vm.network "forwarded_port", guest: 1880, host: 1880
  # MQTT - connection to external brokers
  config.vm.network "forwarded_port", guest: 1883, host: 1883
  config.vm.network "forwarded_port", guest: 8883, host: 8883
  # MongoDB
  config.vm.network "forwarded_port", guest: 27017, host: 27017
  # Portainer.io
  config.vm.network "forwarded_port", guest: 8000, host: 8000
  config.vm.network "forwarded_port", guest: 9443, host: 9443

  config.vm.provision :docker
  config.vm.provision :docker_compose, yml: "/vagrant/docker-compose.yml", run: "always"
end