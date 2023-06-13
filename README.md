# GIT and GITHUB

<hr>

### Fundamentos en la terminal

- **pwd**: Conocer donde se encuentra el user

- **cd .. "file name"**: para desplazarse a un directorio dentro del local

- **mkdir _directory-name_**: para crear un directorio donde se encuentra el user

- **rmdir _directory-name_**: para eliminar un directorio donde se encuentra el user

- **touch _file-name_**: para crear un archivo(file) en el espacio de trabajo del user

- **rm _file-name_**: para eliminar un archivo (file) donde se encuentra el user

- **cat _file-name_**: para ver el contendido de un archivo

- **ls**: para conocer los archivos que estan dentro de la carpeta donde esta el user

- **history**: los comandos utilizados durante un periodo de tiempo

### GIT COMMAND

#### **USER CONFIGURE**

- Conocer la versión instalada en equipo

  ```
  git --version
  ```

- configuracion global de usuario

  ```
  git config --global user.name "user name"
  ```

- configuracion global de correo

  ```
  git config --global user.email "user.name@mail.com"
  ```

- configuracion solo para un repositorio

  ```
  git config user.name "user name"
  ```

- configuracion solo para un repositorio

  ```
  git config user.email "user.name@mail.com"
  ```

- Iniciar repositorio

  ```
  git init
  ```

- Cambio de master a main
  ```
  git config --global init.defaulBranch main
  ```
  Se borra el archivo .git oculto y se realiza el "git init"

#### LAS 3 AREAS DE GIT

| Directorio de trabajo                                 | Area de preparada                                                            | Repositorio                                                                                        |
| ----------------------------------------------------- | ---------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------- |
| Working Directory                                     | Staged                                                                       | Repository                                                                                         |
| Estados modificados localmente pero no son rastreados | Estan en una etapa que estan listos para que sean ubicados en un repositorio | **commit** Archivos agregados en repositorios y marca un punto de salida, para que sean rastreados |
| _no staged_                                           | _process_                                                                    | _commit_                                                                                           |

#### GIT STATUS

Conocer el estado de un directorio/archivo siempre y cuando hayan sido colocados en el Staged.

- opcion para agregar al staged un archivo en especifico

  ```
  git add "file_name"
  ```

- opcion para agregar de manera general

  ```
  git add .
  ```

- remover del staged (estado de preparacion)
  ```
  git rm --cached "name file"
  ```

#### QUE ES UN COMMIT

En una línea de tiempo se toma un fotografía, un registro o cambio en ese archivo; el cual se podrá rastrear en los registros que se realicen
Almacedos con el metodo HASH describiendo cuando se realizó, donde se realizo y quien lo realizo.
![description of commit](pic/pic-1.png)

**SHA**: Secure Hash Algorithms

- commit en línea de comando

```
git commit -m "description of track or job"
```

![commit en terminal](pic/pic-2.png)

- commit en editor de trabajo (siempre y cuando se haya configurado)
  se abre una pagina en el IDE y se podra comentar el commit y al cerrar la pagina, automaticamente se guarda los cambios

  ```
  git commit (dar enter)
  ```

  ![commit en IDE](pic/pic-3.png)

- conocer los cambios realizados durante el periodo de trabajo

  ```
  git log
  ```

  ![Log de trabajos realizado](pic/pic-4.png)

- Asociando el IDE desde comando bash

  ```
  git config --global core.editor "code --wait"
  ```

  donde code es para vs code

- Modificando un commit (localmente)
  Esta operación será por el momento aplicable para el último commit realizado

  ```
  git commit --amend
  ```

  Luego de haber realizado el cambio, se guarda la modificación y se cierra el editor.

- Reversión o elimando el último commit

  Esta opción es aplicable en local, lo mas conveniente es hacerlo antes de subirlo al repositorio. Existen dos tipos de reset _soft_ y _hard_, por el momento solo se hace referencia al _soft_

  ```
  git reset --soft HEAD~1
  ```

  ![Antes de borrar un commit](pic/pic-5.png)
  Mostrando el ultimo commit

  ![Despues de borrar un commit](pic/pic-6.png)
  El commit ultimo ya no existe

#### BRANCH

Branch o ramas, son derivaciones identicas o versiones que provienen desde el main y que son necesarias cuando se requiere realizar un cambio, pero sin afectar lo que se encuentra en producción. Posee todas las caracteristicas necesarias que tiene un _main_, desde hacer un commit hasta que son aplicables al repositorio.

- creando un branch desde main

  ```
  git branch name_description
  ```

  ![Creacion de un branch](pic/pic-7.png)

  Conocer en que rama se encuentra solamente es necesario

  ```
  git branch
  ```

- Cambiar de branch

  ```
  git checkout version-javascript
  ```

  ![desplazamiento de rama](pic/pic-8.png)
  Considerese que el _\*_ indica en que se rama se encuentra

- Creando un rama en un solo comando

  ```
  git checkout -b version-python
  ```

  _-b_ es el indicativo de branch, esta operacion hace que se ubique en la rama recien creada

  ![Creando con un solo comando](pic/pic-9.png)

- cambio de nombre a un branch

  Esto se puede realizar de 2 maneras, la primera consiste en ingresar a la rama y desde alli, realizar el cambion con el siguiente comando

  ```
  git branch -m version-js
  ```

  ![cambio de nombre](pic/pic-10.png)

  El segundo metodo en necesario encontrarse en la rama _main_ y ejecutar el comando

  ```
  git branch -m version-name version-new
  ```

  ![cambio](pic/pic-11.png)
