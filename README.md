These are a set of base containers for Centos, and some additional images with newer versions of Tomcat and Openjdk. Building them is fairly simple.

checkout this repo:

`git clone https://github.com/ssilbory/base_containers.git`

Build base Centos image: (Note that all containers depend on this container!)

`docker build -f Dockerfile.centos.base -t centos-nova-base:7 .`

Build Centos http/php image:

`docker build -f Dockerfile.centos.http -t centos-nova-http:7 .`

Build Centos tomcat image:

`docker build -f Dockerfile.centos.tomcat -t centos-nova-tomcat:7 .`

Build alternate Centos tomcat images: 

`docker build -f Dockerfile.centos.java8 -t centos-nova-java8:7 .`

`docker build -f Dockerfile.centos.tomcat8 -t centos-nova-tomcat8:7 .`

`docker build -f Dockerfile.centos.tomcat9 -t centos-nova-tomcat9:7 .`

Note that if you are planning on just running java the centos-nova-tomcat or the centos-nova-java8 should be used to save space.  The tomcat images are mostly just java, and it's deps, which means a jdk image will just end up costing you more space.  The centos-nova-java8 image was created primarily to share java8 installation between the centos-nova-tomcat8 and centos-nova-tomcat9 images.
