===================================================================================
-En este documento menciono cosas que tuve que hacer para personalizar mi terminal-
===================================================================================

Primero tuve que actualizar algunas cosas. Tuve problemas con el sistema Parrot con repositorios desactualizados
y la clave GPG inválida. Esto suele pasar por algún tiempo sin actualizar el sistema. Antes de proceder con la instalación
de Zsh, debemos asegurarnos de actualizar los repositorios y la clave GPG.

Utilicé esta secuencia de comandos:

1- wget https://deb.parrot.sh/parrot/pool/main/p/parrot-archive-keyring/parrot-archive-keyring_2024.12_all.deb  
   sudo dpkg -i parrot-archive-keyring_2024.12_all.deb

2- sudo apt update

3- sudo apt upgrade -y

Una vez instalado todo esto, podemos proceder a instalar Zsh con:

4- sudo apt install zsh -y

Luego de instalar Zsh podemos instalar los plugins típicos con:

5- sudo apt install zsh-autosuggestions zsh-autocomplete zsh-syntax-highlighting -y

Luego de hacer esto debemos hacer 3 instalaciones bien rápidas: **lsd**, **batcat**, **nerdfonts**

6.0- sudo apt install lsd -y  → ajustar sus alias en el archivo ~/.zshrc  
6.1- sudo apt install bat -y  → ajustar sus alias en el archivo ~/.zshrc

Sugerencia de ajuste de alias en el `.zshrc`:

# alias personalizados  
alias cat="bat"  
alias ls="lsd"  
alias ll="lsd -l"  
alias la="lsd -a"  
alias lla="lsd -la"

6.2- wget https://github.com/ryanoasis/nerd-fonts/releases/latest/download/Meslo.zip  
     unzip Meslo.zip -d ~/.fonts  
     fc-cache -fv  
     Hacer ajuste de fuentes directamente en la terminal (Editar > Preferencias de perfil > General > Tipografía)

Luego de eso instalamos PowerLevel10k desde el repositorio de Romkatv (buscar el más actualizado).  
Entrar al perfil, buscar la sección “MANUAL” y ejecutar:

7- git clone --depth=1 https://github.com/romkatv/powerlevel10k.git ~/powerlevel10k  
   echo 'source ~/powerlevel10k/powerlevel10k.zsh-theme' >> ~/.zshrc

Luego de esto, activar la Zsh para el usuario principal y también para root.  
Podemos hacer un `which zsh` para confirmar la ruta de Zsh y luego ejecutar:

8.0- sudo usermod -s /usr/bin/zsh moika  
8.1- sudo usermod -s /usr/bin/zsh root

Una vez hecho esto, solo falta confirmar con:

9.0- cat /etc/passwd | grep moika  
     moika:x:1000:1001:Moika:/home/moika:/usr/bin/zsh  
9.1- cat /etc/passwd | grep root  
     root:x:0:0:root:/root:/usr/bin/zsh

Después de esto, mayormente el sistema no cambiará de shell así como así.  
Tendremos que reiniciar el sistema para que se ajuste todo:

10- reboot

Luego del reinicio, basta ejecutar:

11- p10k configure

Aquí se configura PowerLevel10k (importante tener las Nerd Fonts instaladas antes de hacer esto).

Luego de instalar la p10k, esto automáticamente añadirá configuraciones al `.zshrc`.  
Este archivo debemos copiarlo al usuario root (ya que root aún no tiene p10k):

12.0- sudo cp /home/moika/.zshrc /root/  
12.1- sudo cp /home/moika/.p10k.zsh /root/
