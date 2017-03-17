ELK Installation using Ansible Playbook

Components that will be Installed using this Playbook:

1. OpenJDK
2. ElasticSearch
3. Kibana
4. Logstash

This has been tested on RHEL 7.3 

Instructions:

git clone https://github.com/sureshgans/elk-ansible.git
cd elk-ansible
Run the playbook: ansible-playbook elk.yml

Directory Structure

├── elk.yml
├── group_vars
│   └── all.yml
├── hosts
├── README.md
└── roles
    ├── elasticsearch
    │   ├── files
    │   │   └── elasticsearch.repo
    │   └── tasks
    │       └── main.yml
    ├── kibana
    │   ├── files
    │   │   └── kibana.repo
    │   └── tasks
    │       └── main.yml
    └── logstash
        ├── files
        │   └── logstash.repo
        ├── tasks
        │   └── main.yml
        └── templates
            ├── 01-beats-input.conf.j2
            ├── 02-syslog-filter.conf.j2
            └── 03-elasticsearch-output.conf.j2

12 directories, 13 files

After Installation, use the AWS public IP and access port 5601
ex: http://{Public IP}:5601/status
