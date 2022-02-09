# <u>Cheatsheet de git</u>

***
## 💻 Crear un repo
Tenés una idea: lo primero que hay que hacer es armar un directorio y `git init`

Luego:
1. `git config --global user.name "Gustavo"`
2. `git config --global user.email "em@il.com"`

Primero suele ser normal crear el README.md y poner ahí de qué va la cosa.

Luego trabajás, creás, hacés, rompés. Acá hay cosas que vemos después.
Pero en resumen:
1. `git add .`
2. `git commit -m 'Mensaje'`

Luego, para el *remote* hay que ir a la página de github/gitlab y crear el repo.
1. \+
2. New repository
3. Seguís los pasos que dice ahí.

Ahora:
1. `git branch -M main`
2. `git remote add origin https://github.com/kildegaard/cheatsheets.git`
3. `git push -u origin main`

***

## OPCIÓN NUEVA: USANDO GITHUB-CLI

Existe GitHub CLI ahora que facilita el uso de los repositorios mediante líneas de comando.
Para esto lo que hay que hacer primero es *instalarlo* desde la [página oficial](https://cli.github.com/)

Los comandos más comunes son sencillos:

- Primero debemos haber inicializado un repo git en la carpeta en la que estamos: `git init -b main`
- Luego tenemos que crear el proyecto, para lo cual: `gh repo create nombre-del-proyecto`. Ahí se sigue al menú interactivo y básicamente eso es todo!
- Lo único que restaría es pullear lo que hay en el repo (asumiendo que creaste un .gitignore), a la vez que se settea el **upstream**: `git pull --set-upstream origin main`

***
## COMANDOS GIT MÁS COMUNES

Acá la idea es ir poniendo los comandos más habituales y usados al emplear git. Los más básicos:

- `git add <algo>`: Con este comando se añade a la *staging area* (desde el *working directory*) archivos y carpetas creados o modificados
- `git commit -m 'mensaje'`: Realizar el commit de todo aquello que se agregó a la *staging* al local repo o HEAD
- `git push` o `git pull`: enviar al repo remoto o traer lo que allí se subió
- `git fetch`: Descarga la *metadata* del repositorio remoto y avisa si hay cambios, sin descargarlos al repo local
- `git merge`: mete lo del local repo (HEAD) al working directory

- `git diff HEAD`: comparar los archivos locales con los commiteados

- `git diff`: compara lo del working directory y lo que está en la staging

- `git clone <repo>`: crea copia local de un remote repo en la compu

## ELIMINANDO CAMBIOS

Tenemos varias etapas:
1. `Working directory`
2. `Staging area` o `index`
3.  `local repository` o `head` o `Cosas commiteadas`
4. `remote repository` o `lo que está en inet`

Un archivo puede estar en 3 estados:

1. commiteado: está guardado en HEAD
2. modificado (o agregado): no están grabados en el local repo, no están protegidos de ninguna manera
3. staged: es parte del index (se taggeo para ser agregado en el siguiente commit)

## COMANDOS ÚTILES

- Hacer que `git branch` muestre las ramas en terminal (y no en vim): `git config --global pager.branch false`

## TEMA BRANCHES

Secuencia de comandos para trabajar con ramas.

- Crear rama: `git branch <nombre-rama>`
- Cambiar a rama: `git checkout <nombre-rama>`
- Subir rama a remoto: `git push <nombre-rama> main`
- Borrar rama (local): `git branch -d <nombre-rama>`
- Borrar rama (remoto): `git push origin --delete <nombre-rama>`
