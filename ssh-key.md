## Crear una clave SSH para acceder a servidores sin contraseña

En el computador local:
```bash
ssh-keygen
```
🗯️ Si se dejan vacíos los campos que pide, se va a guardar en la carpeta por defecto y con el nombre por defecto:

```bash
Enter file in which to save the key (/home/ylo/.ssh/id_rsa):
Enter passphrase (empty for no passphrase):  Enter same passphrase again:
```

## Copiar la clave al servidor al que se quiere acceder sin contraseña
```bash
ssh-copy-id -i ~/.ssh/id_rsa usuario@ip-o-dominio
```

## Probar la nueva clave
```bash
ssh -i ~/.ssh/id_rsa usuario@ip-o-dominio
```

😙
