Vagrant.configure("2") do |config|
  config.vm.box = "precise64"
  config.vm.provision "docker",
    images: ["ubuntu"]

  config.vm.network :forwarded_port, host: 5000, guest: 5000
  config.vm.provision "shell",
    inline: "cd /vagrant && docker build -t mine . && docker run -d -p 5000:5000 mine"
end
