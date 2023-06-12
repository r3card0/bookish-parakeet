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


