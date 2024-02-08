# Como usar múltiples cuentas de GitHub en la misma máquina

## Configuracion
1. Nos dirigimos a 
> C:\Users\clive_pfl66ry\.ssh
Creamos la llave privada & pública. Cambiar "example@gmail.com" y "github-account1"
<ssh-keygen -t ed25519 -C "example@gmail.com" -f github-account1>

ejemplos:
* ssh-keygen -t ed25519 -C "soptec.cjsc@gmail.com" -f soptec
* ssh-keygen -t ed25519 -C "cliver.js.t@gmail.com" -f clijst

2. Configuración de las cuentas a conectar vía SSH.
Host github-account1
  Hostname github.com
  IdentityFile ~/.ssh/github-account1
  IdentitiesOnly yes
  User git

3. 
[3.1] Inicializar repositorio // [3.2] Clonar repositorio
git init                     // git clone

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