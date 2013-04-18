Vagrant::Config.run do |config|
  config.vm.box = "peachy"
  config.vm.network :hostonly, "192.168.2.2"
  # httpd port forwarding
  config.vm.forward_port 80, 8888
  # mysql port forwarding
  config.vm.forward_port 3306, 3306
  # mount srv from local machine
  config.vm.share_folder "v-srv", "/srv", "../srv", :nfs => true
  # Start httpd
  config.vm.provision :shell, :inline => "service httpd start"
  # Start custom stuff
  config.vm.provision :shell, :path => "../srv/vagrant/init.sh"
end
