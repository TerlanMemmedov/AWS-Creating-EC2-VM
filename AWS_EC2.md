Controls the file (existing,available or not) and shows permissions of the file. The example has shown at the below
```
ll YOUR_KEY_NAME.pem 
```
```
ll EC2Key.pem 
```
<br />
<br />


Changes the permissions of the file, all to open and accessible
```
sudo chmod 777 YOUR_KEY_NAME.pem
```
```
sudo chmod 777 EC2Key.pem
```
<br />
<br />


Connecting to our instance on Ubuntu. If you encounter question like "Are you sure you want to continue connecting", Write: yes
```
sudo ssh -i YOUR_KEY_NAME.pem ubuntu@YOUR_PUBLIC_IPV4_ADDRESS_OFF_INTANCE
```
```
sudo ssh -i EC2Key.pem ubuntu@54.205.43.185
```
<br />
<br />


For downloading and adding repository for Amazon Corretto 11 - Java jdk
```
 wget -O- https://apt.corretto.aws/corretto.key | sudo apt-key add - 
 sudo add-apt-repository 'deb https://apt.corretto.aws stable main'
```
<br />
<br />


Installing Corretto 11
```
sudo apt-get update; sudo apt-get install -y java-11-amazon-corretto-jdk
```
<br />
<br />


Verifies the installation and shows the version
```
java -version
```
<br />
<br />


If you see a version string which doesn't mention Corretto, run the command to change the default java or javac providers.
```
sudo update-alternatives --config java
```
```
sudo update-alternatives --config javac
```
<br />
<br />


Uninstalling Amazon Corretto 11
```
sudo dpkg --remove java-11-amazon-corretto-jdk
```
<br />
<br />
