# -*- mode: ruby -*-
# vi: set ft=ruby :

projects_folder   = 'projects'
ram               = '1024'
cpu_max_usage     = '90'

Vagrant.configure("2") do |config|
  config.vm.box       = 'precise32'
  config.vm.box_url   = 'http://files.vagrantup.com/precise32.box'
  config.vm.hostname  = 'base-dev-box'

  config.vm.network :forwarded_port, guest: 8080, host: 8888
  config.vm.network :forwarded_port, guest: 3000, host: 3000
  config.vm.network :private_network, ip: '10.11.12.13'

  config.vm.synced_folder projects_folder, "/#{projects_folder}", :nfs => true

  config.vm.provider :virtualbox do |vb|
    vb.customize ['modifyvm', :id, '--memory', ram]
    vb.customize ['modifyvm', :id, '--cpuexecutioncap', cpu_max_usage]

    # Boot in GUI mode
    # vb.gui = true
  end

  config.vm.provision :shell, :inline => 'sudo apt-get update -qq -y --fix-missing'

  config.vm.provision :puppet,
   :manifests_path => 'puppet/manifests',
   :module_path    => 'puppet/modules'

end
