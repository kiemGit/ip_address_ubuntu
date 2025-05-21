# ip_address_ubuntu
setting ip address ubuntu server

# copy script bellow
    + sudo nano /etc/netplan/00-installer-config.yaml

cara 1
# input file [00-installer-config.yaml] as below
    network:
      renderer: networkd
      ethernets:
        eth0:
          addresses:
            - 192.168.0.38/24
          nameservers:
            addresses: [192.168.0.1]
          routes:
            - to: default
              via: 192.168.0.1
      version: 2
      
cara 2     
# input file [00-installer-config.yaml] as below
    network:
      ethernets:
        eth0:
          dhcp4: false
          addresses: [192.168.0.42/24]
          gateway4: 192.168.0.6
          nameservers:
            addresses: [192.168.0.6]
      version: 2

for ubuntu 25.04 
# create file [/etc/netplan/01-netcfg.yaml]
    network:
      version: 2
      renderer: networkd
      ethernets:
       enp2s0:
        dhcp4: false
        addresses:
          - 192.168.0.4/24
        gateway4: 192.168.0.6
        nameservers:
          addresses: [192.168.0.6]
