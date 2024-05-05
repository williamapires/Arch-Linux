Se você tem uma impressora/scanner HP e não consegue fazer funcionar:

# 1
Instale os seguintes pacotes:
```
sudo pacman -S cups ghostscript gsfonts hplip sane simple-scan cups
```
# 2
Inicie os serviços:
```
sudo systemctl enable cups.service
sudo systemctl start cups.service
```
# 3
Adicione seu usuário aos grupos:
```
sudo gpasswd -a USUARIO scanner
sudo gpasswd -a USUARIO lp
```
Lembrando de substituir USUARIO pelo seu usuario.
# 4
Rode o comando abaixo para detectar seu equipamento:
```
sudo hp-setup -i
```
Vai aparecer algumas opções para selecionar, na maioria dos casos é uma multifuncional usb. Se esse for seu caso, basta dar um ENTER na primeira pergunta.
Depois ele te pergunta se vc quer dar um nome pra impressora, etc. Eu particularmente só vou dando ENTER mesmo.
# 5
Agora vamos identificar de novo a impressora para que ela apareça nos apps de scanner, etc.:
```
sudo sane-find-scanner
```
# 6
Agora abra o seguinte arquivo e descomente a linha #hpaio.
Se ela não existir, adicione no final do arquivo e salve.
```
sudo nano /etc/sane.d/dll.conf
```
# 7
Agora só testar se está tudo funcionando corretamente. Eu gosto de reiniciar o PC nessa etapa só pra ter certeza.
