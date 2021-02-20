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
rm -f /var/run/yum.pid // yumlockが、かかったときの対処法  
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
mysql -h xxxxxxx -P 3306 -u xxxx –p xxxx // login

### Tomcat
ca /opt/  
wget http://ftp.yz.yamagata-u.ac.jp/pub/network/apache/tomcat/tomcat-9/v9.0.41/bin/apache-tomcat-9.0.41.tar.gz  
tar -xzvf ~/apache-tomcat-9.0.41.tar.gz  
ln -s /opt/apache-tomcat-9.0.41 /opt/tomcat  

### Java
yum install -y java-1.8.0-openjdk-devel.x86_64

## cloudFormation.yaml
インフラ構築の自動化

## URL
https://openstandia.jp/oss_info/nginx/version/  
https://tomcat.apache.org/download-90.cgi  