# grafanaのインストール方法
EC2のインスタンス上で実施します。
#### 1. インストール
##### 1.1. yumのリポジトリを追加します。
```
$ sudo vi /etc/yum.repos.d/grafana.repo
[grafana]
name=grafana
baseurl=https://packages.grafana.com/oss/rpm
repo_gpgcheck=1
enabled=1
gpgcheck=1
gpgkey=https://packages.grafana.com/gpg.key
sslverify=1
sslcacert=/etc/pki/tls/certs/ca-bundle.crt
```
##### 1.2. yumコマンドでインストールします。
```
$ sudo yum install grafana -y
--- 省略 ---
Installed:
  grafana.x86_64 0:8.2.2-1   
--- 省略 ---
  xorg-x11-font-utils.x86_64 1:7.5-21.amzn2                                                                       
  xorg-x11-server-utils.x86_64 0:7.7-20.amzn2.0.2                                                                 

Complete!
```
##### 1.3. インストールされたこと確認します。
```
$ yum list installed grafana
Loaded plugins: extras_suggestions, langpacks, priorities, update-motd
Installed Packages
grafana.x86_64                                          8.2.2-1                                           @grafana                 
```
#### 2. サービス設定
##### 2.1. daemonの自動起動設定と起動
```
$ sudo systemctl enable grafana-server.service
Created symlink from /etc/systemd/system/multi-user.target.wants/grafana-server.service to /usr/lib/systemd/system/grafana-server.service.
$ sudo systemctl start grafana-server.service
```
#### 2.2. 起動確認
```
$ sudo systemctl status grafana-server.service
● grafana-server.service - Grafana instance
   Loaded: loaded (/usr/lib/systemd/system/grafana-server.service; enabled; vendor preset: disabled)
   Active: active (running) since Mon 2021-10-25 07:54:43 UTC; 6s ago
     Docs: http://docs.grafana.org
 Main PID: 18076 (grafana-server)
   CGroup: /system.slice/grafana-server.service
           └─18076 /usr/sbin/grafana-server --config=/etc/grafana/grafana.ini --pidfile=/var/run/grafana/grafan...

Oct 25 07:54:43 ip-172-31-39-113.ap-northeast-1.compute.internal grafana-server[18076]: t=2021-10-25T07:54:43+0...
--- 省略 ---
```
active (running)と表示されていれば成功です。
#### 3. ブラウザでアクセスできるか確認します。
```
http://<ホスト名>:3000
```
下記のように表示されれば成功です。
![image](https://user-images.githubusercontent.com/91726058/138657629-08b0c8dd-ab78-4fd9-86e9-3cd6abdd71f5.png)
* ホスト名の確認方法は[EC2インスタンスへの接続方法](../../aws/connect_ec2_instance/README.md)の「2.2」をご確認ください。
* 初期のusename/paswordはどちらも「admin」です。
