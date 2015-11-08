# ansible-mpich2-raspbian

This is an ansible playbook for installing MPICH2 on a raspbian cluster.

1. Install ansible: apt-get install ansible
2. Set up public/private key authentication between your client and the servers (root user)
3. Add the ip of the nodes to ansible/hosts file
4. Run: ansible-playbook main.yml -i <pathToHostsFile>
