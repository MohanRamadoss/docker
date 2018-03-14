
Tomcat9 on CentOS 7


docker build -t mohan:centos-tomcat9 .
groupadd tomcat
useradd tomcat 

mkdir -p /opt/tomcat/webapps  /opt/tomcat/logs

chmod -R 777 /opt/tomcat/

chown -R tomcat:tomcat /opt/tomcat/ 

docker run -v /opt/tomcat/webapps:/opt/tomcat/webapps -v /opt/tomcat/logs:/opt/tomcat/logs -p 8080:8080 -i -t --name tomcat9  mohan:centos-tomcat9

docker run -p 8080:8080 -i -t --name tomcat9  mohan:centos-tomcat9

docker start ff56768fe34d


docker rmi centos-tomcat9:latest
docker images -a
docker rmi mohan:latest
docker images -a


/root/docker/mohan/centos-tomcat9v1 

docker build -t mohan:centos-tomcat9v1 .  

docker run -v /opt/tomcat/webapps:/opt/tomcat/webapps -v /opt/tomcat/logs:/opt/tomcat/logs -p 8080:8080 -i -t --name tomcat9v1  mohan:centos-tomcat9v1


docker build -t mohan:centos-tomcat8v1 .
mkdir -p /opt/tomcat8/webapps  /opt/tomcat8/logs
chmod -R 777 /opt/tomcat8/

docker run  -p 8080:8080 -i -t --name tomcat8v1  mohan:centos-tomcat8v1

docker run -v /opt/tomcat8/webapps:/opt/tomcat/webapps -v /opt/tomcat8/logs:/opt/tomcat/logs -p 8080:8080 -i -t --name tomcat8v1  mohan:centos-tomcat8v1

