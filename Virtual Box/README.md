O Virtual Box pode apresentar um problema com kernel na hora de executar uma MV.  
Pra resolver esse problema é só não esquecer de instalar os modulos quando for instalar o Virtual Box:
```
sudo pacman -S virtualbox virtualbox-host-modules-arch
```
Depois é só reiniciar e sistema e tudo vai funcionar.
---

Para quem usa kernel zen:

```
sudo pacman -S virtualbox virtualbox-guest-iso
yay -S linux-zen-headers virtualbox-ext-oracle #skip zen-headers if you use generic kernel
sudo gpasswd -a $USER vboxusers
sudo modprobe vboxdrv

sudo systemctl enable --now vboxweb.service
```
