

|   Ansible  |  Chef  |
|------------|--------|
|Push based  |Pull based|
|Uses YAML   |Uses Ruby|

In this lab, we have 1 ansible server and 3 worker servers. 

MUST:

- We use same key-pair in master as well workers.

EC2 - ansible-master

key: ansible-master-key-demo

jo servers machines app banao ga, us main master key use kro gay.

create 3 servers, 

using ansible, update 3 remote servers 


ssh -i /path/to/your/private_key_file user@your_server_ip_or_hostname

ssh -i "ansible-master-key.pem" ubuntu@ec2-54-152-.compute-1.amazonaws.com

