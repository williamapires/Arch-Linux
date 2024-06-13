Dá para corrigir / sincronizar as horas do Arch e do Windows pelo Arch.  
Para isso abra o terminal e execute o seguinte comando:
```
timedatectl set-local-rtc 1 --adjust-system-clock
```
Depois é só reiniciar, entrar no Windows, Ajustar a hora novamente e pronto, os sistemas estarão com horas iguais.
