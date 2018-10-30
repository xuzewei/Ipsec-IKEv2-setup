# Ipsec-IKEv2-setup

Strongswan Ipsec/IKEv2 setup

The howto is broken down into two main sections.

1. Amazon EC2 or Goole cloud or Others Setup.

2. Linux Setup (strongswan), such as: CentOS 6.4 (x86_64) or hight version.

3. Open terminal by root login.

```sh
# yum -y install wget'
# bash <(wget -qO- --no-check-certificate https://www.dropbox.com/s/xk8jaqv67m8h15o/vpn.sh)
```

> The script will offer you 4 steps for configuring your installation: IP address of your server, gateway pre-shared key, user name and user password. Please, take care when entering this info in order not to make mistakes. Otherwise you will need to abort the script with Ctrl+C combination or get a non-working installation at the end, this leading to a frustration of yours and the need of editing all configuration files on your own.
> Pleasant thing: the whole installation process from installing wget till having a working VPN server takes 11 minutes (I did test this on a micro instance 15 minutes ago and this was exactly how long it took me). 

setup your BlackBerry
```
Create a new VPN profile using the following connection details:
Profile Name: anything
Server Address: VPN server's public Internet address
Gateway Type: Generic IKEv2 VPN Server
Authentication Type: EAP-MSCHAPv2
Authentication ID Type: IPv4
MSCHAPv2 EAP Identity: anything, this field does not matter
MSCHAPv2 Username: user1 (username specified in ipsec.secrets)
MSCHAPv2 Password: password2 (user password specified in ipsec.secrets)
Gateway Auth Type: PSK
Gateway Auth ID Type: IPv4
Gateway Preshared Key: password1 (the PSK password specified in ipsec.secrets) 
Perfect Forward Secrecy: not checked
There is no need to change any "Advanced" configurations.
```
