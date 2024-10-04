This ansible playbook deploys a patroni cluster across 2 different datacenters. It sets up the entire server including creation of the required directories, user equivalence to login from the step server, Monitoring, backup, creation of some critical extensions in the template 1 database, crontab with some necessary scripts. 

Stack : 
OS         - Rocky 8 / Rocky 9
Postgres   - 12/14/15 (Including pg_profile, pg_partman, pg_stat_kcache, pg_wait_sampling)
Patroni    - 3.1
Pgbackrest - 2.45

To run the playbook : 
sudo ansible-playbook -i inventory pg_patroni_build.yml
