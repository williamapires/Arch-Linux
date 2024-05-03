# Como resolver quando seu HD externo ou interno em NFTS não quer montar e apresenta alguma mensagem de erro:

## 1

Instale o pacote para suporte ao sistema de arquivo:
```
sudo pacman -S ntfs-3g
```

## 2

Rode o seguinte comando com o caminho do seu HD em específico:
```
sudo ntfsfix -d /dev/xxx
```

O sistema deve retornar uma mensagem de sucesso, se tudo for bem, como no exemplo a baixo:
```
Mounting volume... OK
Processing of $MFT and $MFTMirr completed successfully.
Checking the alternate boot sector... OK
NTFS voluem version is 3.1.
NTFS partition /dev/sdc1 was processed successfully.
```

## 3

Agora você consegue ir no seu gerenciador de arquivos e acessar normalmente seu HD.
