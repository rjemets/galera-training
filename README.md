# galera-training
Ansible playbooks for setting up a MariaDB Galera cluster.

1. SELinux and IPTables rules must be disabled or set up manually on target hosts before running these playbooks.
2. Put your Galera cluster options into group_vars/galera-training/galera-options.json file.
3. For each cluster node create a dedicated directory under host_vars/,
   copy the host_vars/galera-test1.local/galera_options.json there and edit options accordingly.
4. Include each node's hostname under galera-training group in the hosts file.
5. Run the playbooks/install_galera_server.yml against the whole server group or individual hosts using 'nodes' variable
   in the ansible-playbook command line.
6. Bootstrap the first node and run the create_replication_user.yml against that host.
7. Start up secondary cluster nodes and check the cluster status.
