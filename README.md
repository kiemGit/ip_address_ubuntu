# ip_address_ubuntu
setting ip address ubuntu server

# copy script bellow
    + sudo nano /etc/netplan/00-installer-config.yaml

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
