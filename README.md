This ansible playbook deploys a patroni cluster across 2 different datacenters. It sets up the entire server including creation of the required directories, user equivalence to login from the step server, Monitoring, backup, creation of some critical extensions in the template 1 database, crontab with some necessary scripts. 

Stack : 
OS         - Rocky 8 / Rocky 9
Postgres   - 12/14/15 (Including pg_profile, pg_partman, pg_stat_kcache, pg_wait_sampling)
Patroni    - 3.1
Pgbackrest - 2.45

To run the playbook : 
sudo ansible-playbook -i inventory pg_patroni_build.yml


--To run from jenkins : 
sudo ansible-playbook /postgres_auto/pg_ansible/playbooks/patroni_build/patroni_jenkins.yml --extra-vars="WSDC_hosts=${WSDC_hosts} SADC_hosts=${SADC_hosts} db_version=${Postgres_version} env=${Environment} cluster_name=${Cluster_name} app_name=${Application_name} db_owner=${Database_owner} group_dl=${Group_DL} db_env=${Database_environment} app_tier=${Application_tier} app_id=${Application_ID} network_zone=${Network_zone}"
