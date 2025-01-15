Crear maquina virtual con ubuntu en virtualbox

Establecer el adaptador 1 como NAT y el dos como anfitrion

Entrar en /etc/netplan y editar el archivo 50… añadiendo lo siguiente:

```bash
# This file is generated from information provided by the datasource.  Changes
# to it will not persist across an instance reboot.  To disable cloud-init's
# network configuration capabilities, write a file
# /etc/cloud/cloud.cfg.d/99-disable-network-config.cfg with the following:
# network: {config: disabled}
network:
    ethernets:
        enp0s3:
            dhcp4: true
        enp0s8:
            dhcp4: false
            addresses: [192.168.56.10/24]
    version: 2
```
