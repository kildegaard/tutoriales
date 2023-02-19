# Manejando Linux como un campeón

## Comandos básicos

- `cp [opción] origen destino`: copia directorio/archivo
- `mv [opción] origen destino`: mueve directorio/archivo
- `rm [opción] origen destino`: elimina directorio/archivo
- `mkdir <directorio>`: crea directorio

Opciones:

- -i: interactivo: te pregunta para sobreescribir
- -r: recursivo: repite todo en las subcarpetas (si copiás, copia todo tal cual)
- -v: verbose: te va diciendo lo que pasa

Ejemplos: rm data1.txt, data2.txt, data3.txt:	borra los 3 archivos

- `ls`: búsqueda
- `ls -h`: búsqueda (te dice el tamaño de los cosos en kB, MB, ...
- `sudo apt upgrade <nombre app>`: Actualizar algún programa en particular
- `cd`: Vuelve a home/gus/
- `.`: Hacer referencia al lugar en donde estás parado (Es lo mismo que `source`)
- `xdc-open archivo`: Abrir archivo con programa predeterminado
- `ln -s ~/path/de/interes ~/path/destino`: Crear accesos directos
- `tar -xf <file>`: Unzipear un tar.xz
- `cat foo >> bar`: Concatenar dos archivos desde terminal

- `date`: Fecha
- `cal`: Calendario
- `df -h`: Tamaño ocupado de los discos
- `du -h`: Te dice cuánto ocupa lo que sea que le pases (Es como el Windirstat!)
  - `du -a`: hace que liste todos los archivos y su tamaño
- `ps axc | grep <programa>`: ps te muestra programas corriendo, axc hace que se vea un poco mejor. El pipe ( | ) es para pasarle el resultado a otra app en este caso "grep" que hace algo así como búsqueda de lo que le pongas adelante, en este caso el programa <programa>
- `top`: Tipo program manager
- `htop`: Más colorido
- `gotop`: Mucho más cheto
- `ip <addr>`: Te da la data de la IP
- `ping <algo>`: Exactamente eso



***
## ffmpeg

Comandos más útiles de la aplicación

- `ffmpeg -f concat -safe 0 -i milista.txt -c copy output.mp4`: Concatenar varios videos en uno solo sin cambiar nada más
- `milista.txt` es un archivo de texto que se crea así:
    - cat > milista.txt: Ahí te deja tipear, tenés que ir agregando los archivos así:
        - `file '/ruta/al/archivo'`
        - `...`
        - `Ctrl + D`

Splitear videos en tamaños determinados

- `ffmpeg -i input.mp4 -t 01:00:00 -c copy output.mp4`: crea un video de una hora desde el inicio
- `ffmpeg -i input.mp4 -ss 01:00:00 -t 01:00:00 -c copy output.mp4`: eso crea un video de una hora DESDE el tiempo 01:00:00
- `ffmpeg -i input.mp4 -ss TIEMPO_desde -to TIEMPO_hasta -c copy output.mp4`: Reducir la calidad (y por ende el tamaño)
- `ffmpeg -i input.mp4 -vcodec libx264 -crf 35 output.mp4`: Reduce la calidad. 1 < crf < 50 Mientras más grande, más reduce y más calidad se pierde. Crf estándar : 23
- Cuando convertís muchos videos a veces te tira error de buffer... agregar esta linea a los parámetros
    -max_muxing_queue_size 1024
- `ffmpeg -i input.mp4 -c:v libxvid output.mp4`: Convertir a un codec que se banca Android (xvid)

***
## youtube-dl

Es para descargar videos de youtube (en principio) pero puede bajar video, audio, todo junto y también de otros lugares (udemy, ...)

* youtube-dl <URL>

* `youtube-dl -F <URL>` : este te tira una lista de las versiones que se pueden bajar

* `youtube-dl -f N <URL>`: descarga ese videito (o lo que sea)

* `youtube-dl -a 'batch.txt'`: podés armar un batch con una URL por cada renglón y te los baja todos

* `youtube-dl -o 'videoOutput.mp4' <URL>`: te guarda ese nombre de video

***
## anaconda

- source ~/anaconda3/bin/activate root
- conda python
- conda spyder
- conda update --all
- conda deactivate

## Comandos útiles

- Instalar archivos .deb: `dpkg -i path/al/archivo.deb` y luego `sudo apt install -f`
- Instalar archivos .tar.gz: `tar -xzf archivo.tar.gz`, luego entrás a la carpeta que se crea y ahí `./configure`. Luego, `make` y, finalmente, `sudo make install`
