# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

# this is somewhat awful but i am using nocm variants of the boxes,
# to run puppet from the shared filesystem. but that means some setup
# is needed to prepare the environment then propagate it through sudo
myscript = <<END
rpm -Uvh rpm -Uvh https://dl.fedoraproject.org/pub/epel/epel-release-latest-7.noarch.rpm
yum -y install tmux git the_silver_searcher zsh
adduser -G wheel -s /bin/zsh eric
END

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  # Every Vagrant virtual environment requires a box to build off of.
  config.vm.define :cloudline do |cloudline_config|
    # slice stuff goes here
    cloudline_config.vm.provision :shell, inline: myscript
  end
end
