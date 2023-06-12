# Git - GitHub commands


# Comandos básicos en Git
Crear una carpeta llamada proyecto1. Ubicarse en la carpeta creada. 

## Crea un repositorio de Git y haz tu primer commit

### Crear un repositorio
Para crear un repositorio es necesario indicar donde (carpeta/directorio) se almacenara la información. Una vez ubicados en la capeta principal del proyecto, ejecutar el comando git init.

Se puede ejecutar VSCode desde la terminal. Solo se ejecuta el comando **code . .**. En mi caso no ocurrió nada. Para que se corriera, tuve que hacer lo siguiente en VSCode:

### ¿No te funciona el comando ```code```en tu terminal?
1. Abre Visual Studio Code
2. Presiona ```cmd + shift + p ``` o si estás en windows ``` ctrl + shift + p ```
3. Buscar una opción que diga lo siguiente: ```Shell Command: Install 'code' command in $PATH ``` y seleccionarla

# Cambio de nombre del repositorio principal
Para configurar el nombre inicial de la rama principal de un repositorio para usar en todos los repositorios, se pued usar el siguiente comando:
```
git config --global init.defaultBranch "main"
```

Para cambiar el nombre del repositorio de forma local unicamente para el repositorio elegido y no el general, se puede usar el siguiente comando:
```
git branch -m "name"
```

# GitHub
## Configurar llaves SSH
Las llaves son por persona (equipo)
* Configurar user.name y user.email en el ambiente local de *git*
* Revisar la configuración del momento con el comando: ```git config -l ```

## Crear las llaves publica y privada
* En terminal, en el directorio home, correr el script:
    ```
    ssh-keygen -t rsa -b 4096 -C "<email del repositorio de github>"
    ```
    Ejecutar *enter*
    
    Texto que aparece en la terminal
    ```
    Generating public/private rsa key pair.
    Enter file in which to save the key (home/.ssh/id_rsal):
    ```
    Ejecutar *enter*. Se recomienda mantener la ruta  que se muestra en el texto que aparece en la terminal.
    ```
    Created directory 'home/.ssh'.
    Enter passphrase (empyt for no passphrase):
    ```
    Implementar el password deseado (passphrase) y ejecutar *enter* o bien solo ejecutar *enter* y quedará sin passphrase.
    ```
    Your identification has been saved in home/.ssh/id_rsa.
    Your public key has been saved in home/.ssh/id_rsa.pub
    The key fingerprint is:
    whatever numbers email del repositorio de github
    The key's randomart image is:
    +---[RSA 4096]---+
    aqui se despliega una imagen
    +---[SHA256]---+
    
## Checar que la llave privada jale en Windows
En terminal, escribir la siguiente linea de codigo:
```
eval $(ssh-agent -s)
```
Ejecutar *enter* y si esta jalando debe aparecer algo asi en terminal
```
Agent pid whatevernumber
```
* El texto *Agent* indica que el servidor de llaves está corriendo bien en windows
* el texto *pid* es el identificador del proceso (process id)
    



