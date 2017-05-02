# Ansible Playbook - Setup Storm Cluster.  

This is a simple Storm Cluster Setup.

Below is how the Storm Cluster was deployed.


                            / ---- supervisor01
    Nimbus[nimbus and ui]-----
                            \ ---- supervisor02


## Step 1: Update Hosts File.

Update the host file to reflect your server IPs.
Currently `hosts` file looks as below.

    [zookeeper]
    192.168.33.100 zookeeper_id=1
    192.168.33.101 zookeeper_id=2
    192.168.33.102 zookeeper_id=3

    [storm]
    192.168.33.100
    192.168.33.101
    192.168.33.102

    [storm-nimbus-ui]
    192.168.33.100

    [storm-supervisor]
    192.168.33.101
    192.168.33.102


## Step 2: Executing.

Below is the command when used against Vagrant with insert new key set to False.

    $ ansible-playbook --private-key=~/.vagrant.d/insecure_private_key -u vagrant -i hosts ansible_storm.yml
