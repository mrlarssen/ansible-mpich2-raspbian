This is an ansible playbook for installing MPICH2 on a raspbian cluster. With small changes to the paths the yaml file, this can be used for any OS as long as python and gcc is present on the servers.

Prerequisites:
Public/private key authentication between your client and the servers (as root)

# Install and configure (user root)

Note: If you want the latest version of mpich2, you should change the version name in the yaml file in the following tasks:<br/>
INSTALL MPICH2 <br/>
UNARCHIVE MPICH2 <br />

1. Install ansible: apt-get install ansible
2. Add the ip of the nodes to ansible/hosts file
3. Run: ansible-playbook main.yml -i hosts <br/> Be patient. This step might take up to an hour. <br/>If it finishes with no errors, you now have MPICH2 up and running!

# Testing (user pi)
4. Choose a "master" node, and go to /home/pi/mpich2/.
5. Set up public/private key authentication between this node and the other nodes in your cluster
6. cd /home/pi/mpich2 and create a file 'machinefile' and add the ips to all your nodes in the cluster including this machine.
7. Run mpi example: mpiexec -f machinefile -n <numberOfNodes> build/examples/cpi

