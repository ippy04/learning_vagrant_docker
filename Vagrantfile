VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = 'docker-ubuntu-12.04.3-amd64-vbox'
  config.vm.box_url = 'https://oss-binaries.phusionpassenger.com/vagrant/boxes/ubuntu-12.04.3-amd64-vbox.box'
  config.vm.network :forwarded_port, guest: 3000, host: 3000
  config.vm.synced_folder './project', '/project'
 
  config.vm.provision 'docker'
 
  
  cmd = "docker build -t rails /project/."
 
  config.vm.provision :shell, :inline => cmd
 
  config.vm.provision 'docker' do |d|
    d.run 'rails',
    args: '-v /project:/project -p 3000:3000'
  end
end
