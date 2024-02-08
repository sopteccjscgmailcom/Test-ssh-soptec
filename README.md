# Como usar múltiples cuentas de GitHub en la misma máquina

## Configuracion
1. Nos dirigimos a la sig ruta y si no encontramos creamos la carpeta .ssh
  C:\Users\[tusuario]\.ssh
2. Luego Creamos la llave privada & pública. Cambiar "correo@gmail.com" y "github-account1"
    ssh-keygen -t ed25519 -C "correo@gmail.com" -f github-account1

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

# agregamos
    git init
# cualquiera de los 2
    git clone

## Establecemos el correo de la cuenta cada que inicializamos o clonamos un repositorio.
    config user.email "correo@gmail.com"

#### otros ejemplos
    git config user.email "soptec.cjsc@gmail.com"

##### mas
      git config user.email "cliver.js.t@gmail.com"

### Hacemos cambion normales a nuestro repositorio
    git add .

### Guardar cambios
  git commit -m "first commit"

### !IMPORTANT Poner el nombre de la llave que creamos 
    git remote add origin git@github-account1:correo@gmail.com/test.git


##### Publicar cambios
    git push origin master