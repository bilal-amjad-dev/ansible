

```bash
vim deploy_static_page_play.yml
```

```bash
-
 name: Install Nginx and server static website
 hosts: prd
 become: yes # it for root user
 tasks:
  - name: Install Nginx
    apt:
     name: nginx
     state: latest

  - name: Start Nginx
    service:
     name: nginx
     state: started
     enabled: yes
  
  - name: Deploy web page
    copy:
     src: index.html
     dest: /var/www/html
```

Esc:wq!


```bash
vim index.html
```

```bash
<!DOCTYPE html>
<html>
<body>

<h1>Bilal Amjad</h1>

</body>
</html>
```

Esc:wq!

```bash
ansible-playbook deploy_static_page_play.yml
```
