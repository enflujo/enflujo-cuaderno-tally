# Configurar [pm2](https://pm2.keymetrics.io/docs/usage/quick-start/) para reiniciar aplicaciones en el servidor automáticamente

## Comprobar si está instalado pm2
```bash
pm2 status
```
Si no está instalado correr en debian:

```bash
apt update && apt install sudo curl && curl -sL https://raw.githubusercontent.com/Unitech/pm2/master/packager/setup.deb.sh | sudo -E bash -
```
:exclamation: Para revisar que el comando anterior esté actualizado revisar la documentación [aquí](https://pm2.io/docs/runtime/guide/installation/).

## Configurar el hechizo (script) para iniciar automáticamente los procesos

```bash
pm2 startup
```

## Congelar la lista de procesos que se inician automáticamente

```bash
pm2 save
```

❗Si se actualiza la versión de Node, revisar que el pm2 se reinicie en esa versión. Es posible que haya que actualizar la ruta con un comando similar a este, que sale en el terminal sugerido por pm2:

```bash
sudo env PATH=$PATH:/home/$usuario/.nvm/versions/node/v20.10.0/bin /home/$usuario/.nvm/versions/node/v20.10.0/lib/node_modules/pm2/bin/pm2 startup systemd -u $usuario --hp /home/$usuario
```

## Comprobar que pm2 funciona correctamente e inicia los procesos

* Reiniciar el servidor:
```bash
sudo reboot
```
* Una vez reiniciado el servidor comprobar el estado de pm2
  
```bash
pm2 status
```
Si los procesos están online = 😸😸. 
Ejemplo:

![image](https://github.com/enflujo/enflujo-cuaderno-tally/assets/5365329/14a12d81-93f7-4336-b173-b9a18b7cfe38)

