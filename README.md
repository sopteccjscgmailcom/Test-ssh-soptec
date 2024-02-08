# Como usar múltiples cuentas de GitHub en la misma máquina

## Configuracion en PC
#### 1. Nos dirigimos a la sig ruta y si no encontramos creamos la carpeta .ssh
    C:\Users\[tusuario]\.ssh

#### 2. Luego Creamos la llave privada & pública [Cambiar "correo@gmail.com" y "github-account1"]
    ssh-keygen -t ed25519 -C "correo@gmail.com" -f github-account1

##### ejemplos para crear 2 llaves para correos diferentes
    ssh-keygen -t ed25519 -C "soptec.cjsc@gmail.com" -f soptec
    ssh-keygen -t ed25519 -C "cliver.js.t@gmail.com" -f clijst

#### 3. Creamos un archivo config para poner nuestra configuracion de cuentas a conectar vía SSH.
    Host github-account1
      Hostname github.com
      IdentityFile ~/.ssh/github-account1
      IdentitiesOnly yes
      User git

    Host github-account2
      Hostname github.com
      IdentityFile ~/.ssh/github-account2
      IdentitiesOnly yes
      User git

## Configuracion en GitHub
pronto

## Como Usar
#### 1. Creacion del repositorio local
    git init
    git clone https://github.com/correogmailcom/test.git
Inicializar repositorio  o clonamos un repositorio

#### 2. Establecemos el correo de la cuenta cada que inicializamos o clonamos un repositorio.
    config user.email "correo@gmail.com"

##### otros ejemplos
    git config user.email "soptec.cjsc@gmail.com"
    git config user.email "cliver.js.t@gmail.com"

#### 3. Hacemos cambion normales a nuestro repositorio
    git add .

#### 4. Guardar cambios
    git commit -m "commitNormal"

#### 5. ☣!Important Poner el nombre de la llave que creamos cuando hacemos la conexion al repositorio
    git remote add origin git@github-account1:correo@gmail.com/test.git

##### 6. Publicar cambios
    git push origin master