# My-Marven-Script-
# this is used to add maven to your linux server 
# first create a maven hostname 
sudo hostname maven
# then change into the hostname using sudo su ec2-user or the user you are working with.
cd /opt
yum install wget nano tree unzip git-all -y
yum install java-11-openjdk-devel java-1.8.0-openjdk-devel -y
java -version
git --version

#2. Install Maven.sh
#------------------

#Step1) Download the Maven Software allways check the current version on the maven website before runing the bellow code

wget https://dlcdn.apache.org/maven/maven-3/3.8.3/binaries/apache-maven-3.8.3-bin.zip

unzip apache-maven-3.8.3-bin.zip
rm -rf apache-maven-3.8.3-bin.zip
mv apache-maven-3.8.3/ maven

Step3) Set Environmental Variable  -  For Specific User
----------------------
#vi ~/.bash_profile
echo "export M2_HOME=/opt/maven" >> ~/.bash_profile
echo "export PATH=$PATH:$M2_HOME/bin" >> ~/.bash_profile

<<m2
#Step3b) Set Environmental Variable  For All Users
---------------------- 
echo "export M2_HOME=/opt/maven" >>  /etc/profile
echo "export PATH=$PATH:$M2_HOME/bin" >> /etc/profile

step4) Activate the maven home and mvn by running the below scripts
source /etc/profile

Step5) Check the Maven version
m2
source ~/.bash_profile
mvn -version
# this will install maven to your server 
