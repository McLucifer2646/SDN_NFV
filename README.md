# SDN_NFV
Software Defined Networking and Network Function Virtualization

### Installing Mininet

#### For Ubuntu 20.04 -> Installation from Packages

- [Reference](http://mininet.org/download/#option-3-installation-from-packages)

Install the base Mininet package by entering the following command
```
sudo apt-get install mininet
```

To check the installed Mininet Version:
``` mn --version```

Mininet supports multiple switches and OpenFlow controllers. For this test, we will use Open vSwitch in bridge/standalone mode

To test if the mininet is installed and working well, use the following command in the installation directory
```
sudo mn --switch ovsbr --test pingall
```

To get a list of available softwares for installation under mininet
```
mininet/util/install.sh -h
```

If you wish to go through the Mininet walkthrough, you will want to install additional software. The following commands will install the OpenFlow reference switch, reference controller and Wireshark dissector.
```
git clone https://github.com/mininet/mininet
mininet/util/install.sh -fw
```

### Installing OpenDayLight (ODL)




## Author 

- **Anshul Madurwar** 
