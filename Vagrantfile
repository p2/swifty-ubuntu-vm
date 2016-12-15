Vagrant.configure(2) do |config|
  config.vm.box = "ubuntu/xenial64"
  
  # Create a shared folder for easy development
  config.vm.synced_folder "../Ubuntu-Share", "/macOSshare"
 
  config.vm.provision "shell", inline: <<-CMD
    sudo apt-get update
    sudo apt-get --assume-yes install clang libicu-dev libcurl3 libpython2.7
    
    # load and unpack Swift
    curl -O https://swift.org/builds/swift-3.0.2-release/ubuntu1604/swift-3.0.2-RELEASE/swift-3.0.2-RELEASE-ubuntu16.04.tar.gz
    tar zxf swift-3.0.2-RELEASE-ubuntu16.04.tar.gz
    
    sudo chown -R ubuntu:ubuntu swift-*  # replace with `vagrant` in trusty, use `ubuntu` user in xenial
    echo "export PATH=/home/ubuntu/swift-3.0.2-RELEASE-ubuntu16.04/usr/bin:\"${PATH}\"" >> .profile
    echo "Swift has successfully installed on Linux"
  CMD
end
