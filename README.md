#Puppet Enterprise Vagrant Environment

##Dependencies
* VMware Fusion
* Vagrant

##Vagrant Plugins
* Vagrant PE Build
  https://github.com/adrienthebo/vagrant-pe_build
* Vagrant Hosts
 https://github.com/adrienthebo/vagrant-hosts

##Usage
NOTE:  All these examples assume usage with the VMware Fusion provider.  If
you are using VirtualBox, please adjust accordingly.

Add the base box.  I have had great success with PuppetLabs Vagrant
Boxes:

```
$ vagrant box add centos6 http://puppet-vagrant-boxes.puppetlabs.com/centos-64-x64-fusion503-nocm.box
```

 Download PE from puppetlabs.com

 Add PE with the vagrant pe_build plugin:
```
$ vagrant pe-build copy <path_to_pe_tar.gz>
```

Set the version of Puppet Enterprise you will be installing
```ruby
PE_VERSION = '3.3.x'
```

Boot the envionment with the VMware Fusion provider
```
$ vagrant up --provider=vmware_fusion
```

After the environment has booted, you can browse to the Enterprise Console at:

  https://192.168.34.10

##Logging in

  Puppet Master:
  $ vagrant ssh master

  Puppet Node:
  $ vagrant ssh agent1

##Logging into the Console

  Username: admin@puppetlabs.com
  Password: puppetlabs

###TODO
