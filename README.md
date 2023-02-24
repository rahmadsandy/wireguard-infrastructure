# wireguard-infrastructure

this project for educational purpose, fill up my portofolio
setup wireguard server and client, also create monitoring inside



this project using some references

### wireguard web 
https://github.com/vx3r/wg-gen-web

### wireguard exporter
https://github.com/MindFlavor/prometheus_wireguard_exporter

### monitoring
https://github.com/Einsteinish/Docker-Compose-Prometheus-and-Grafana


## Wireguard Server
#### install wireguard
``` bash
add-apt-repository ppa:wireguard/wireguard
apt-get update
apt-get install wireguard-dkms wireguard-tools linux-headers-$(uname -r)
```
#### enable ipv4 forwarding
``` bash
vim /etc/sysctl.conf
```
![3](https://raw.githubusercontent.com/rahmadsandy/wireguard-infrastructure/master/static/sysctl.conf.png)
``` bash
sysctl -p
echo 1 > /proc/sys/net/ipv4/ip_forward
```
#### wireguardserver docker
example env
``` bash
# IP address to listen to
SERVER=0.0.0.0
# port to bind
PORT=8888
# Gin framework release mode
GIN_MODE=release
# where to write all generated config files
WG_CONF_DIR=/data
# WireGuard main config file name, generally <interface name>.conf
WG_INTERFACE_NAME=wg0.conf

# SMTP settings to send email to clients
SMTP_HOST=smtp.gmail.com
SMTP_PORT=587
SMTP_USERNAME=contact@sandysend.com
SMTP_PASSWORD=dlpuiqtfxibinipassword
SMTP_FROM=IT Support <itsupport@sandysend.com>

#fake 
OAUTH2_PROVIDER_NAME=fake

ADMIN_USER=admin
ADMIN_PASSWORD=xxxxxxxxxxxxxxxx
ADMIN_PASSWORD_HASH=JDJhJDA5JHcxSjZTd2gxTFF4dlUzdWJ5Zzdasdadadsasdasdasd0a3FFek44adsadasUlNajljbzVl
WG_STATS_API=http://127.0.0.1:8182
```


## Monitoring (Prometheus & Grafana)
![1](https://user-images.githubusercontent.com/57087446/221109904-8fb90b0e-3e0a-4498-a748-117827361859.png)

![2](https://user-images.githubusercontent.com/57087446/221109951-896c37da-d867-413a-b32a-106c65df0030.png)
