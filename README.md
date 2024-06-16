Este tutorial fue hecho para campus party 2012 Bogota, estan libres de copiarlo y usarlo


esta acompañado de slides si quieren:

Verlas: http://bit.ly/gitCOP5

Copiarlas o Editarlas: http://bit.ly/github-COP5-edit 


# GIT 101 - Conceptos Basicos

## Init

Primero inicializar el repositorio con __git init <nombreRepositorio>__
tambien se puede inicializar una carpeta ya existente ej

    $ cd nombreRepositorio
    nombreRepositorio/$ git init

## Config

Para poder ver que configuraciones tenemos usamos __git config__
ej. el editor de commits o el nombre de usuario

    $ cd nombreRepositorio
    nombreRepositorio/$ git config -l

-l lista todas las configuraciones

    $ git config --global user.name "Su Nombre"
    $ git config --global user.email "Su Correo"
    $ git config --global core.editor "Su Editor ej. notepad"

Esto se hace para configurar la instalacion/repositorio

## Add

Para poder agregar algo a un commit hay que crearlo y luego agregarlo con __git add__

    $ vim README.md
    -- hacer algo alli --
    $ git add README.md

tambien se puede usar __git add -A__ para agregar a un commit todos los cambios
*USAR CON PRECAUCION*

## Commit

Hacer un commit (comprometerse con un cambio :P) luego de agregar los cambios a un commit
se hace usando __git commit__

    $ git commit

**-m** se puede usar para enviar en el commit el mensaje directamente ej. __git commit -m "Primer Commit"__
*USAR CON PRECAUCION*

## Status

Permite visualizar si hay archivos que tienen ambios que pendientes de hacer commit/sobreescribir

    $ git status

## Diff

El commando __git diff__ permite ver a detalle cuales son los cambios que estan
pendientes, con *--* muestra los archivos como se encuentran en el repositorio 
y con *++* los archivos como estan actualmente

## Checkout

Con el commando __git checkout <nombreArchivo/Ficher>__ reemplazo mis cambios
locales por los cambios que se encuentran en el repositorio, adicionalmente me
permite cambiar entre ramas (*ver adelante*)

## Log

__git log__ muestra el log de los commits que se han realizado, incluyendo el mensaje,
el autor, y la fecha

# rm / mv

Con __git rm__ o __git mv__ se pueden eliminar o mover archivos o ficheros que se encuentran
en el repositorio

# GIT 201 - Ramas y Mezclas

## branch

Una rama es un nuevo camino del codigo que debe ser manejado pero que no esta listo para
ser incluido en el *master* del repositorio, (la rama master es la rama por defecto en git) 

las ramas se usan por ejemplo para manejar nuevas funcionalidades

__git branch__ sin argumentos lista la ramas disponibles y con un asterisco la actual 
__git branch -v__ Lista las ramas y muestra el ultimo commit en cada una 
__git branch <nombreRama>__ crea una rama para trabajar
__git branch checkout <nombreRama>__ cambia la rama de trabajo a la rama seleccionada
__git branch checkout master__ vuelve a la rama principal (trunk?)
__git branch -D <nombreRama>__ elimina la rama

Todos los commits que se realizen estando trabajando en una rama quedan en la rama y se puede
cambiar entre ramas sin que los cambios realizados en una u otra se vean reflejados antes 
de hacer una mezcla (*ver adelante*)

## merge

Luego de tener los cambios en una rama y estar seguros de estos hay que realizar una mezcla
existen diferentes estrategias para mezclar ej.
    
    branch->master
    master->branch
    branch->branch
    (branch<->branch)->branch

El commando __git merge__ nos permite hacer todo este tipo de mezclas, sin embargo solo vamos a
ver la mas basica, luego de realizar los cambios en nuestra rama:

    $ git checkout master                # pasamos al master
    $ git merge <nombreRama>             # mezclamos la rama en nuestro master

Si existen conflictos git nos mostrara los archivos donde se presentaron para que sean resueltos
manualmente

## tag / show

Cuando estamos seguros de una version de nuestro codigo y queremos marcarla como segura / estable
podemos crear un tag con __git tag <nombre del tag>__ para que quede una copia del repositorio
en ese momento, para listar los tags lo hacemos con __git tag -l__ y para ver especificamente que 
tiene un tag lo hacemos con __git show <nombre del tag>__

# GIT 301 - Compartiendo el codigo

## .gitignore

Algunos archivos no queremos que sean controlados o guardar copias de estos en el repositorio
por ejemplo .class / .pyc / .py~ etc, para esto creamos un archivo .gitignore que contiene
mediante expresiones regulares los archivos y tipos de archivos que no queremos controlar

## clone

Un repositorio de git esta listo para ser compartido desde el primero momento, para hacer una
copia de un repositorio se debe usar __git clone <ubicacion del repo>__

## SSH Keys

Antes de poder compartir nuestro codigo o colaborar con otros repositorios debemos identificarnos
de una forma que garantize nuestra autenticidad, para esto se usa la generacion de llaves SSH

    $ ssh-keygen

Esto nos genera una llave publica y una llave privada, debemos entregarle la llave publica a la 
persona que queremos que confie en nuestro codigo (ej. github)

## remote

Para poder conectarnos con un repositorio fuera del que tenemos tenemos tenemos que agregar un 
repositorio remoto con el commando __git remote add <nombre remoto> <ubicacion del repo>__ se
puede usar __git remote rm <nombre remoto>__ para borrarlo

## push

Luego de estar conectados a un repositorio podemos _empujar_ al repositorio remoto los cambios
que tenemos en nuestro repositorio local mediante __git push <nombre remoto> <nombre rama>__
por defecto git intenta empujar al remoto origin y a la rama master

## pull y fetch

Al igual que podemos empujar nuestros cambios a un repositorio remoto podemos jalar cambios de
un repositorio remoto a nuestro repositorio local bien sea a nuestro carpeta de trabajo (pull) 
o a la copia de nuestro repositorio (fetch) usando los comandos

__git pull <nombre remoto> <nombre rama>__
__git fetch <nombre remoto> <nombre rama>__

## Fork?

Un fork no es un concepto de Git, es mas una conveniencia social, donde se hace el clone de un 
repositorio bajo un nombre propio, como git genera una copia del repositorio a traves de un

clone, podemos trabajarlo como un






------------------------------------------------------------------------------------------
in English 
# GIT 101 - Basic Concepts

## Init

First, initialize the repository with __git init <repositoryName>__.
You can also initialize an existing folder, e.g.:

    $ cd repositoryName
    repositoryName/$ git init

## Config

To view the current configurations, use __git config__.
For example, the commit editor or the username:

    $ cd repositoryName
    repositoryName/$ git config -l

-l lists all configurations

    $ git config --global user.name "Your Name"
    $ git config --global user.email "Your Email"
    $ git config --global core.editor "Your Editor e.g. notepad"

This is done to configure the installation/repository.

## Add

To add something to a commit, first create it and then add it with __git add__:

    $ vim README.md
    -- make some changes there --
    $ git add README.md

You can also use __git add -A__ to add all changes to a commit.
*USE WITH CAUTION*

## Commit

To commit (commit to a change :P) after adding the changes to a commit,
use __git commit__:

    $ git commit

**-m** can be used to send the commit message directly, e.g. __git commit -m "First Commit"__.
*USE WITH CAUTION*

## Status

Allows you to see if there are files with changes that are pending commit/overwrite:

    $ git status

## Diff

The __git diff__ command allows you to see in detail what changes are pending. With *--*, it shows the files as they are in the repository, and with *++*, it shows the files as they are currently.

## Checkout

With the __git checkout <fileName>__ command, you can replace your local changes with the changes in the repository. Additionally, it allows you to switch between branches (see below).

## Log

__git log__ shows the log of commits that have been made, including the message, the author, and the date.

# rm / mv

With __git rm__ or __git mv__, you can delete or move files or directories in the repository.

# GIT 201 - Branches and Merges

## branch

A branch is a new path of the code that needs to be managed but is not ready to be included in the *master* branch of the repository (the master branch is the default branch in Git).

Branches are used, for example, to manage new features.

__git branch__ without arguments lists the available branches and marks the current one with an asterisk.
__git branch -v__ lists the branches and shows the last commit in each one.
__git branch <branchName>__ creates a branch to work on.
__git checkout <branchName>__ switches the working branch to the selected branch.
__git checkout master__ switches back to the main branch (trunk?).
__git branch -D <branchName>__ deletes the branch.

All commits made while working on a branch remain in that branch, and you can switch between branches without the changes in one branch affecting the others until you perform a merge (*see below*).

## Merge

After making changes in a branch and being sure of them, you need to perform a merge. There are different strategies for merging, e.g.,

    branch->master
    master->branch
    branch->branch
    (branch<->branch)->branch

The __git merge__ command allows us to perform all these types of merges. However, we will only cover the most basic one here. After making changes in our branch:

    $ git checkout master                # switch to master
    $ git merge <branchName>             # merge the branch into master

If there are conflicts, Git will show the files where conflicts occurred so they can be resolved manually.

## Tag / Show

When we are sure about a version of our code and want to mark it as safe/stable, we can create a tag with __git tag <tagName>__ to keep a snapshot of the repository at that moment. To list the tags, use __git tag -l__, and to see what a specific tag contains, use __git show <tagName>__.

# GIT 301 - Sharing the Code

## .gitignore

Some files should not be tracked or stored in the repository, such as .class, .pyc, .py~, etc. For this, we create a .gitignore file that contains regular expressions specifying the files and types of files we do not want to track.

## Clone

A Git repository is ready to be shared from the very beginning. To make a copy of a repository, use __git clone <repoLocation>__.

## SSH Keys

Before sharing our code or collaborating with other repositories, we must authenticate ourselves securely. This is done by generating SSH keys:

    $ ssh-keygen

This generates a public key and a private key. You need to provide the public key to the person you want to trust your code (e.g., GitHub).

## Remote

To connect to a repository outside the one we have, we need to add a remote repository with the command __git remote add <remoteName> <repoLocation>__. To remove it, you can use __git remote rm <remoteName>__.
## Push

Once connected to a repository, we can push our changes to the remote repository using __git push <remoteName> <branchName>__. By default, Git attempts to push to the remote named "origin" and the "master" branch.

## Pull and Fetch

Just as we can push our changes to a remote repository, we can pull changes from a remote repository to our local repository, either to our working directory (pull) or to the copy of our repository (fetch) using the commands:

__git pull <remoteName> <branchName>__
__git fetch <remoteName> <branchName>__

## Fork?

A fork is not a Git concept but more of a social convention. It involves cloning a repository under your own name. Since Git creates a copy of the repository through a clone, we can work with it as our own repository.
