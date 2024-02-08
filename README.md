# Como usar múltiples cuentas de GitHub en la misma máquina

## Configuracion
1. Nos dirigimos a la sig ruta y si no encontramos creamos la carpeta .ssh
  C:\Users\[tusuario]\.ssh
2. Luego Creamos la llave privada & pública. Cambiar "example@gmail.com" y "github-account1"
  ssh-keygen -t ed25519 -C "example@gmail.com" -f github-account1

ejemplos:
* ssh-keygen -t ed25519 -C "soptec.cjsc@gmail.com" -f soptec
* ssh-keygen -t ed25519 -C "cliver.js.t@gmail.com" -f clijst

3. Creamos un archivo config para poner nuestra configuracion de cuentas a conectar vía SSH.
{Host github-account1
  Hostname github.com
  IdentityFile ~/.ssh/github-account1
  IdentitiesOnly yes
  User git

Host github-account1
  Hostname github.com
  IdentityFile ~/.ssh/github-account1
  IdentitiesOnly yes
  User git}

## Creacion del repositorio
3. Inicializar repositorio  o clonamos un repositorio
  git init                     
  
  git clone

4. Establecer correo de la cuenta cada que inicializamos o clonamos un repositorio.
git config user.email "correo@gmail.com"

git config user.email "soptec.cjsc@gmail.com"
git config user.email "cliver.js.t@gmail.com"

5. Agregar cambios
git add .

6. Guardar cambios
git commit -m "first commit"

7. Conectar con repositorio remoto
git remote add origin

8. Publicar cambios
git push origin master