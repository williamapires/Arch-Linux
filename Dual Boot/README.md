Se você é um usuário que precisa ter dual boot em seu sistema e usa Arch Linux, deve ter percebido que o Arch não faz o reconhecimento automatico de outros sistemas e integra tudo ao GRUB.  
Vamos resolver esse problema.  
Lembrando que esse tutorial é para o GRUB!
# 1
Instale os seguintes pacotes:
```
sudo pacman -S ntfs-3g os-prober
```
# 2
Após instalar os pacotes, monte a partição ou HD em que o outro sistema operacional está instalado. Pode ser Windows, outra distro linux, MacOS, etc. Qualquer que for e rode o os-prober para que ele identifique o(s) outro(s) sistemas:
```
sudo os-prober
```
# 3
Agora que você já tem os SO's identificados pelo os-prober, abra o arquivo do GRUB e desmarque a linha: #GRUB_DISABLE_OS_PROBER=false
Salve e feche o arquivo.
```
sudo nano /etc/default/grub
```
# 4
Rode o seguinte comando para que o GRUB seja reconfigurado e liste os SO's:
```
sudo grub-mkconfig -o /boot/grub/grub.cfg
```
# 5
Agora é só reiniciar e ver se está tudo funcionando.
