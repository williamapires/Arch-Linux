O Arch Linux (Vanila) não vem com o serviço de Bluetooh ligado por padrão, como acontece no Fedora. Para ligar esse serviço:  
  
**1 -** Vamos verificar se o serviço está ativo. (Mesmo sabendo que se for uma instalação nova e "Vanila", não vai estar!):
```
systemctl status bluetooth
```
**2 -** Se estiver desabilitado, vamos então ativar esse serviço:
```
systemctl enable bluetooth
```
**3 -** Vamos instalar alguns pacotes necessários:
```
sudo pacman -S bluez bluez-utils
```
**4 -** Agora vamos configurar o serviço de bluetooth.  
Para isso vamos entrar nesse arquivo de configuração:
```
sudo nano /etc/bluetooth/main.conf
```
Dentro da sessão [Policy], desmarque a linha:
```
AutoEnable=true
```
Salve e feche o arquivo ```ctrl+o``` e ```ctrl+x``` respectivamente.  

**5 -** Agora vamos reiniciar o serviço de bluetooth:
```
sudo systemctl restart bluetooth
```
Pronto. Agora é para funcionar sem problemas seu dipositivo bluetooth.
