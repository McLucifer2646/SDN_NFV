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
```mn --version```

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

- [Reference](https://john.soban.ski/install-opendaylight-ubuntu-lts-fast.html)

The following list records the steps necessary to install OpenDaylight on Ubuntu LTS 20.04

Execute an apt-get update, which refreshes the list of available packages.
```
sudo apt-get -y update
```

Now upgrade the packages via the upgrade option.
```
sudo apt-get -y upgrade
```

Install unzip, to unzip the OpenDaylight archive.
```
sudo apt-get -y install unzip
```

The following command installs the JAVA 17 JRE
```
sudo apt-get -y install openjdk-17-jre
```

Use the update-alternatives command as shown below, update-alternatives presents a list of installed Java versions and allows you to select the desired default version.

If update-alternatives provides a list of versions, select JAVA 17 from the list.
```
sudo update-alternatives --config java
```
update-alternatives will output a useful piece of information - the full path to your JAVA executable. Copy this path down, you will need it to set the JAVA_HOME environment variable in the next step.

Retrieve the full path to your JAVA executable. If you lost track, you can run the following command:
```
ls -l /etc/alternatives/java
```

In my case it was:
```
lrwxrwxrwx 1 root root 43 Aug 16 18:49 /etc/alternatives/java -> /usr/lib/jvm/java-17-openjdk-amd64/bin/java
```

OpenDaylight wants the JAVA_HOME environment variable to reflect the location the entire JAVA toolset, and not just the JAVA executable. For that reason, remove bin/java from the path. So the new path becomes: 

```
/usr/lib/jvm/java-17-openjdk-amd64
```

To set (and persist) the value of JAVA_HOME, edit your BASH resource file.
```
echo 'export JAVA_HOME=/usr/lib/jvm/java-17-openjdk-amd64' >> ~/.bashrc
```

Now the JAVA_HOME is initialised as an environment variable and contains the path to the Java Runtime Environment, thus when this is added to the bashrc file, whenever a new terminal is opened, the terminal is already told at the beginning that it might have to run the JRE. THough if it doesn't function for the first run after a restart use the following command.

```
source ~/.bashrc
```

Next We have to download the OpenDaylight Zip Archive, to do this visit the following website:

[https://docs.opendaylight.org/en/latest/downloads.html](https://docs.opendaylight.org/en/latest/downloads.html)

In this installation guide, I will be downloading the latest version of ODL, which is Argon-SR1 (for me), it might be different when you peeps install.

In the Argon-SR1 section, find **OpenDaylight Argon Zip**,
and download the zip archive.

Once downloaded, save it in the home directory and then unzip it using the following command:
```
unzip karaf-0.18.1.zip
```

Finally to run the installed ODL go to the unzipped folder and enter the follwoing command, 
```
./bin/karaf
```

Once you are done, Press ```Ctrl + D``` to exit.


## Author 

- **Anshul Madurwar** 
