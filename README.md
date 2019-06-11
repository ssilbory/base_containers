These a set of base containers for Centos.   Building them is fairly simple.

checkout this repo:

`git clone https://github.com/ssilbory/base_containers.git1`

Build base Centos image:

`docker build -f Dockerfile.centos.base -t centos-nova-base:7 .`

Build Centos http/php image:

`docker build -f Dockerfile.centos.http -t centos-nova-http:7 .`

Build Centos tomcat image:

`docker build -f Dockerfile.centos.tomcat -t centos-nova-tomcat:7 .`

Build tomcat containers:

`docker build -f Dockerfile.tomcat9.jre11 -t tomcat-nova:9-jre11 .`

`docker build -f Dockerfile.tomcat9 -t tomcat-nova:9 .`

`docker build -f Dockerfile.tomcat8 -t  tomcat-nova:8 .`

Note that if you are planning on just running java the centos-nova-tomcat or the tomcat-nova images should be used to save space.  (Most of the tomcat images are just java, and it's deps.)
