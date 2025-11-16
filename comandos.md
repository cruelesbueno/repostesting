============================
COMANDOS BÁSICOS
============================
pwd - muestra el directorio actual
cd - entra a una carpeta
cd .. - sube un nivel
ls - lista archivos
ls -l - lista en formato largo
ls -a - muestra archivos ocultos
clear - limpia la pantalla
mkdir - crea una carpeta
rmdir - elimina carpeta vacía
touch - crea un archivo vacío
cp - copia archivos
mv - mueve o renombra archivos
rm - elimina archivos
rm -r - elimina carpetas con contenido
cat - muestra contenido de archivo
nano - edita archivo en terminal
echo - imprime texto
echo "hola" > archivo.txt - escribe en archivo
echo "hola" >> archivo.txt - agrega texto al final

============================
COMANDOS INTERMEDIOS
============================
sudo - ejecuta algo como administrador
apt update - actualiza lista de paquetes
apt upgrade - instala actualizaciones
apt install paquete - instala un paquete
history - muestra los comandos usados
which comando - muestra la ruta del comando
file archivo - muestra tipo de archivo
man comando - muestra el manual del comando
grep "texto" archivo - busca texto dentro de un archivo
find /ruta -name archivo - busca archivos
tar -xf archivo.tar - extrae .tar
unzip archivo.zip - descomprime .zip
chmod +x archivo - da permisos de ejecución
chmod 755 archivo - permiso estándar
chown usuario:grupo archivo - cambia propietario
df -h - muestra uso de disco
du -h - muestra tamaño de carpetas
ps - muestra procesos en ejecución
top - monitorea procesos en tiempo real
kill PID - mata un proceso
wget URL - descarga archivos
curl URL - obtiene contenido de una URL
ping direccion - prueba conexión
ip a - muestra interfaces de red
ssh usuario@IP - conecta por SSH
scp archivo usuario@IP:/ruta - copia archivos por SSH

============================
COMANDOS ÚTILES (EXTRAS)
============================
neofetch - muestra info del sistema (si está instalado)
htop - alternativa avanzada a top (si está instalado)
batcat archivo - cat mejorado
lsd - ls mejorado

============================
COMANDOS PELIGROSOS (NO USAR)
============================
rm -rf /         ← destruye TODO el sistema
chmod 000 archivo ← elimina todos los permisos
dd if=/dev/zero   ← puede sobreescribir discos
mkfs.ext4 /dev/sdX ← formatea discos completos
