
=====================================
 
Docker Sample On CentOS 7

======================================


git init


git remote add origin https://github.com/MohanRamadoss/docker.git 

git pull  https://github.com/MohanRamadoss/docker.git

git add --all :/

git status

git commit -m 'message'

git push -u origin master


###########################################

  Docker nginx simple web server 


    docker build -t="mohannginx/centos-nginx:v2" .
    
    docker images
    
    docker run -p 80:80 -i -t --name nginxv2 mohannginx/centos-nginx:v2
    
    docker start nginxv2
    
    docker exec -it nginxv2 bash
	
    

    docker build -t="mariadbv1/centos-mariadb:v1" .
    
    docker images
    
    docker run -p 3306:3306 -i -t --name mariadbv1 mariadbv1/centos-mariadb:v1
    
    docker start mariadbv1 

    docker exec -it mariadbv1 bash
	
	

    goinside(){

    docker exec -it $1 bash -c "stty cols $COLUMNS rows $LINES && bash";
    
     }
   
     export -f goinside



#################################

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

#################################

/root/docker/mohan/centos-tomcat9v1 

docker build -t mohan:centos-tomcat9v1 .  

docker run -v /opt/tomcat/webapps:/opt/tomcat/webapps -v /opt/tomcat/logs:/opt/tomcat/logs -p 8080:8080 -i -t --name tomcat9v1  mohan:centos-tomcat9v1


docker build -t mohan:centos-tomcat8v1 .

mkdir -p /opt/tomcat8/webapps  /opt/tomcat8/logs

chmod -R 777 /opt/tomcat8/

docker run  -p 8080:8080 -i -t --name tomcat8v1  mohan:centos-tomcat8v1

docker run -v /opt/tomcat8/webapps:/opt/tomcat/webapps -v /opt/tomcat8/logs:/opt/tomcat/logs -p 8080:8080 -i -t --name tomcat8v1  mohan:centos-tomcat8v1

docker build -t mohan:centos-tomcat9 .

groupadd tomcat

useradd tomcat 

mkdir -p /opt/tomcat/webapps  /opt/tomcat/logs

chmod -R 777 /opt/tomcat/

chown -R tomcat:tomcat /opt/tomcat/ 

docker run -v /opt/tomcat/webapps:/opt/tomcat/webapps -v /opt/tomcat/logs:/opt/tomcat/logs -p 8080:8080 -i -t --name tomcat9  mohan:centos-tomcat9

docker run -p 8080:8080 -i -t --name tomcat9  mohan:centos-tomcat9

docker start ff56768fe34d



#################################

docker rmi centos-tomcat9:latest

docker images -a

docker rmi mohan:latest

docker images -a


#################################
/root/docker/mohan/centos-tomcat9v1 

docker build -t mohan:centos-tomcat9v1 .  

docker run -v /opt/tomcat/webapps:/opt/tomcat/webapps -v /opt/tomcat/logs:/opt/tomcat/logs -p 8080:8080 -i -t --name tomcat9v1  mohan:centos-tomcat9v1



#################################
docker build -t mohan:centos-tomcat8v1 .

mkdir -p /opt/tomcat8/webapps  /opt/tomcat8/logs

chmod -R 777 /opt/tomcat8/


docker run  -p 8080:8080 -i -t --name tomcat8v1  mohan:centos-tomcat8v1

docker run -v /opt/tomcat8/webapps:/opt/tomcat/webapps -v /opt/tomcat8/logs:/opt/tomcat/logs -p 8080:8080 -i -t --name tomcat8v1  mohan:centos-tomcat8v1


#################################

docker build -t mohan:centos7-apache24-php .

docker run -p 80:80 -p 443:443 -d -v /app/html/:/var/www/html --name apache24-php  mohan:centos7-apache24-php 

#################################

docker build -t mohanreverseproxy:php7 .

docker run -dt -p 80:80 -p 443:443 -e PROXY_GATEWAY="/" -e PROXY_DESTINATION="http://192.168.1.21:8080" --name="reverse-proxy" mohanreverseproxy:php7



#####Apache webserver#####

docker build -t mohanapache:reverse .

docker run -dt -p 80:80 -p 443:443  --name="reverse-proxy" mohanapache:reverse


#####tomcat 9#######

cd centos-tomcat9

docker build -t mohan:centos-tomcat9 .

docker run -v /opt/tomcat/webapps:/opt/tomcat/webapps -v /opt/tomcat/logs:/opt/tomcat/logs -p 8080:8080  -p 8009:8009 -i -t --name tomcat9  mohan:centos-tomcat9


#################################
