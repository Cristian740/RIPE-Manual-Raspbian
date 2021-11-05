# RIPE-Manual-Raspian

Para crear e instalar el paquete de software en un Raspberry Pi, siga las instrucciones:

1. Actualizar los paquetes.
```
sudo apt update
```
2. Instalar los paquetes de requisitos necesarios para compilar e instalar el software de la sonda:
```
sudo apt update && sudo apt install git tar fakeroot libssl-dev libcap2-bin autoconf automake libtool build-essential
```
3. Por recomendación, crear un directorio donde se clonará el software de la sonda. Luego acceder a este directorio
```
mkdir RIPE
cd RIPE
```
4. Clonar el repositorio del software de la sonda:
```
git clone --recursive https://github.com/RIPE-NCC/ripe-atlas-software-probe.git
```
5. Construir el paquete Debian (*.deb*)
```
./ripe-atlas-software-probe/build-config/debian/bin/make-deb
```
6. Instalar el paquete *.deb*
```
sudo dpkg -i atlasswprobe-??????.deb
```
7. Verificar el registro del software de la sonda:
```
cat /var/atlas-probe/etc/probe_key.pub
```

Posteriormente, registrar la clave pública (obtenida en el paso 7) en el siguiente link: [registrar el probe](https://atlas.ripe.net/apply/swprobe/), para lo cual se debe [crear una cuenta en RIPE](https://access.ripe.net/registration) previamente.
