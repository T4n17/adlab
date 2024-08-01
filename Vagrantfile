Vagrant.configure("2") do |config|
  config.vm.box_check_update = false

  config.vm.define "bt01" do |bt01|
    bt01.vm.box = "t4n17/tinykali"
    bt01.vm.box_version = "1"
    bt01.vm.synced_folder '.', '/vagrant', disabled: true
    bt01.vm.network "forwarded_port", guest: 22, host: 2222, id: 'ssh'
    bt01.vm.network "private_network", ip: "192.168.56.15"
    bt01.ssh.username = "root"
    bt01.ssh.password = "bt01"

    bt01.vm.provider :virtualbox do |vb|
        vb.name = "bt01"
    end
  end

  config.vm.define "dc01" do |dc01|
    dc01.vm.box = "t4n17/ws22"
    dc01.vm.guest = :windows
    dc01.vm.communicator = "winrm"
    dc01.winrm.username = "Administrator"
    dc01.winrm.password = "AdminPassword1$"
    dc01.vm.network "forwarded_port", guest: 3389, host: 3389
    dc01.vm.network "private_network", ip: "192.168.56.4", auto_config: false
    dc01.vm.synced_folder '.', '/vagrant', disabled: true

    dc01.vm.provider :virtualbox do |vb|
      vb.name = "dc01"
    end
  end

  config.vm.define "user01" do |user01|
    user01.vm.box = "t4n17/win10"
    user01.vm.guest = :windows
    user01.vm.communicator = "winrm"
    user01.winrm.username = "User01"
    user01.winrm.password = "User01Password1$"
    user01.vm.network "forwarded_port", guest: 3389, host: 3388
    user01.vm.network "private_network", ip: "192.168.56.5", auto_config: false
    user01.vm.synced_folder '.', '/vagrant', disabled: true

    user01.vm.provider :virtualbox do |vb|
      vb.name = "user01"
    end
  end

end
