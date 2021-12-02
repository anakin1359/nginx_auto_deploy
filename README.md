Role Name
=========
* nginx: Nginxサーバの設定を行うRole
* wordpress: Wordpressの設定を行うRole

Variables
--------------
* group_vars
  * work_usr: 公開用ディレクトリの所有者/グループを指定してください。
  * public_dir: 「/var/www/${work_usr}」がNginxを起動した際の公開ディレクトリとなります。
  * etc: 「./roles/nginx/file/default.conf」内の`location`先を上記の`public_dir`と合わせる必要があります。

etc
--------------
* OS: centos7以降のみ動作します（centos6以前は正常に動作するようにしていません）

Playbook
--------------
* Connection test
```
ansible system1 -m ping -i hosts/develop_nginx_server
```

* Dryrun
```
ansible-playbook -i hosts/develop_nginx_server nginx.yml --check
```

* Run the playbook
```
ansible-playbook -i hosts/develop_nginx_server nginx.yml --step
```