


### Installation of Ansible

```bash
sudo apt-addrepository
ppa:ansible/ansible
```
// we are installing ansible repository in our system

```bash
sudo apt update
```

```bash
sudo apt install ansible
```


```bash
ansible --version
```


### Update Host file:

```bash
sudo vim /etc/ansible/hosts
```




```bash
[servers]
server1 ansible_host=<Public IP>
server2 ansible_host=<Public IP>
server3 ansible_host=<Public IP>
```


### Send `ansible-master-key-demo.pem` from your local computer to ansible server

No1. Create key folder in ansible machine `mkdir keys`

No2. Run Scp (source copy)command in your local machine

scp -i "ansible-master-key-demo.pem" ansible-master-key-demo.pem ubuntu@ec2-54-152-.compute-1.amazonaws.com:/home/ubuntu/keys




chmod 400 ansible-master-key-demo.pem



No3. in your ansible server:

cd keys
ls

you can see the key has come here 


Update hostfile

```bash
sudo vim /etc/ansible/hosts
```

```bash
[servers]
server1 ansible_host=<Public IP>
server2 ansible_host=<Public IP>
server3 ansible_host=<Public IP>
```

```bash
[servers:vars]
ansible_python_interpreter=/usr/bin/python3
ansible_user=ubuntu
ansible_ssh_private_key_file=/home/ubuntu/keys/ansible-master-key-demo.pem
```

Esc:wq!

### Ping all servers

```bash
ansible servers -m ping 
```

yes

server1 | SUCCESS => {
    "changed": false,
    "ping": "pong"
}


