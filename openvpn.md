# Welcome to TechPark repository!

Hi! If you want to learn more about IT and DevOps, Subscribe my  channel  [**TechPark**](https://www.youtube.com/channel/UClM-3NJDYp8GKMlQ0tgIjUg) 

 

## Install and Configure OpenVPN on AWS EC2 and make a VPN connection 
### youtube video [**link**](https://youtu.be/-8qySFJ5z7o)

 
### EC2 configuration
I'm using the amazon linux v2 image for this setup.
Open port 943 and 443 is open in Security Group associated with the server. 
Open port 1143 and 1194 for client connection from anywhere or from specific IP or target.


### Install OpenVPN access server on Amazon Linux
```
yum -y install https://as-repository.openvpn.net/as-repo-amzn2.rpm
yum -y install openvpn-as
```
Check the status of service using
```
Systemctl status openvpnas.service
```
Now configure the openvpn using root permission
```
/usr/local/openvpn_as/bin/ovpn-init --force
```

### OpenVPN client installation
```
 apt install apt-transport-https
 
curl -fsSL https://swupdate.openvpn.net/repos/openvpn-repo-pkg-key.pub | gpg --dearmor > /etc/apt/trusted.gpg.d/openvpn-repo-pkg-keyring.gpg

curl -fsSL https://swupdate.openvpn.net/community/openvpn3/repos/openvpn3-focal.list >/etc/apt/sources.list.d/openvpn3.list

 apt update && apt install openvpn3 
```


### Connect 

Download user locked profile in your computer and run following commands 
```
openvpn3 session-start  --config <profile.ovpn>
```
### List connected session
```
openvpn3 sessions-list
```
### To discount from VPN 
```
openvpn3 session-manage --disconnect --config <profile.ovpn>
```


