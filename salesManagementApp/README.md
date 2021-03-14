# salesManagementApp　アプリ開発サークル(共同開発)

## AWS Skill
Amazon Virtual Private Cloud(VPC)  
Subnet  
RouteTable  
InternetGateWay  
Elastic IP Address    
NAT gateWay  
Network ACL  
SecurityGroup  
Amazon Elastic Compute Cloud(EC2)  
Elastic Block Store(EBS)  
Amazon Relational DataBase Service(RDS)  

## EC2 install
nginx  1.19.2  
Apache Tomcat 9.0.41  

## Use Command 
yum update  
ps aux |grep "yum update" //update確認コマンド  
ssh -i xxxx.pem ec2-user@x.x.x.x // 接続用  

### Nginx
amazon-linux-extras // installできるpackageの確認  
amazon-linux-extras install nginx1  
cp -a nginx.conf nginx.conf_back // /etc/nginx/nginx.conf backupファイル作成しておく  
amazon-linux-extras | grep nginx  自動起動確認  
systemctl enable nginx  // nginx自動起動  
systemctl start nginx  // nginx起動  
systemctl status nginx　// 設定確認  

### Mysql
yum localinstall -y https://dev.mysql.com/get/mysql80-community-release-el7-2.noarch.rpm // mysqlRepository  
yum install -y mysql-community-server // インストール  
systemctl start mysqld // 起動   
systemctl status mysqld // 状態確認  
mysql -h test3.xxxx.xxxx.rds.amazonaws.com -P 3306 -u admin –p  //ログイン

### nginx .conf
vim /etc/nginx/nginx.conf 

location / {
           proxy_pass http://localhost:8080; // リバースプロキシ設定
        }

### useful Command
rm -f /var/run/yum.pid // yumlockが、かかったときの対処法  
sudo nslookup xxxx.xxxxx.xxxx.rds.amazonaws.com // dnsサーバーの設定の情報を調べる  

### Java
yum install -y java-1.8.0-openjdk-devel.x86_64
yum install -y java-11-amazon-corretto-headless // java11

alternatives --config java // java変更コマンド

### 起動
java -jar xxxx-0.0.1-SNAPSHOT.jar  

## cloudFormation.yaml
インフラ構築の自動化

## URL
https://openstandia.jp/oss_info/nginx/version/  
https://tomcat.apache.org/download-90.cgi  // tomcat使う場合url