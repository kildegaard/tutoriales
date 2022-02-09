# Instalando los Drivers de Nvidia en Debian 11 (un bardo...)

1. Bajar los drivers de la página oficial (yo me bajé `NVIDIA-Linux-x86_64-495.44.run`)
2. Instalar los pre-requisitos: `apt -y install linux-headers-$(uname -r) build-essential libglvnd-dev pkg-config`
3. Deshabilitar el driver `nouveau`: `echo blacklist nouveau > /etc/modprobe.d/blacklist-nvidia-nouveau-conf`
4. Reiniciar en modo CLI: `systemctl set-default multi-user.target`. Esto hay que hacerlo en modo superusuario
5. Reiniciar: `systemctl reboot`
6. Va a arrancar en modo no gráfico. Hay que logearse, ir a la carpeta donde está el archivo (Downloads por ejemplo) y de ahí correr: `bash NVIDIA-Linux-x86_64-495.44.run`
7. Luego va por un tubo (?) Para volver a habilitar el tema gráfico: `systemctl set-default graphical.target`
8. Último reboot: `systemctl reboot`

# Cómo desinstalar TODO en caso que algo salga mal

Podemos revisar si tenemos paquetes instalados (porque quizás mandamos un `sudo apt remove nvidia-driver` pero queda de todo dando vueltas). Para esto: `dpkg -l | grep -i nvidia`

Luego para reventar todo: `sudo apt remove --purge '^nvidia-.*'` y nos vimos!
