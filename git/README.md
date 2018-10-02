# Comandos git (alias de zsh)

### Help

```
$ git help
$ git help COMANDO
```

### Config

Usuario y correo:
```
$ git config --global user.name "NOMBRE"
$ git config --global user.email "CORREO"
```

Listar configuración:
```
$ git config --global --list
$ git config --list
```

### Init

Iniciar repo:
```
$ git init
$ git init RUTA
```

### Clone

Clonar proyecto:
```
$ git clone RUTA
```

Clonar proyecto sin historial:
```
$ git clone RUTA_REMOTA --depth 1 --branch NOMBRE_BRANCH --single-branch DIRECTORIO
```

### Status

Estatus del repositorio
```
$ git status
```

### Log

Registro de commits:
```
$ git log
$ git log --oneline
$ git log --graph
```

### Add

Agregar archivo/cambio:
```
$ git add NOMBRE
```

Agregar todos los archivos/cambios:
```
$ git add -A
```

Agregar dinamicamente:
```
$ git add -p
```

### Commit

Commit cambios:
```
$ git commit -m "MENSAJE"
```

Commit cambios y agregar:
```
$ git commit -am "MENSAJE"
```

Commit cambios:
```
$ git commit --amend -m "MENSAJE"
```

Editar commit: Antes se puede hacer add de algo
```
$ git commit --amend -m "MENSAJE"
```

### Pull

**Descargar cambios remotos y fusionar:**
```
$ git pull
$ git pull origin master
```
En caso de conflictos, resolverlos y luego:
```
$ git add -A
```   
Hacer commit y push


**Pull rebase: Al tener commits**
```
$ git pull -r
```    
En caso de conflictos, resolverlos y luego:
```
$ git add -A
$ git rebase --continue
```

### Push

Borrar rama remota:
```
$ git push REMOTE :NOMBRE
```

Enviar cambios:
```
$ git push
$ git push origin
$ git push REMOTO
$ git push REMOTO BRANCH (crea rama)
$ git push -f
$ git push -u origin master (-u recordar parametros)
```

Enviar cambios a rama master desde ejemplo:
```
$ git push remoto ejemplo:master
```    

Subir tag (-f forzar):
```
$ git push origin --tags
$ git push origin TAG
$ git push REMOTO TAG
```

### Reset

Reset archivo:
```
$ git reset --soft ARCHIVO
$ git reset --soft HEAD ARCHIVO
```

Eliminar commit sin tocar el fuente:
```
$ git reset --soft SHA
$ git reset --soft HEAD^
$ git reset --soft HEAD^^ (dos commit atras)
```

Eliminar commit completamente:
```
$ git reset --hard SHA
```

Limpiar proyecto en punto actual completamente:
```
$ git reset --hard
```

Eliminar ultimo commit atras:
```
$ git reset --hard HEAD~1
$ git reset --hard HEAD^
```

Eliminar varios commit atras:
```
$ git reset --hard HEAD~NUMERO
```

Limpiar commits hasta upstream:
```
$ git reset --hard @{u}
```

Borrar commit en github:
```
$ git reset --hard <sha-commit-name-to-go-back-to>
$ git push -f origin HEAD^:master
```

### Checkout

Ir a branch o archivo:
```
$ git checkout NOMBRE
```

Ir a commit:
```
$ git checkout SHA
```

Restaurar archivo desde commit:
```
$ git checkout SHA NOMBRE
```

Descartar cambios (para wip):
```
$ git checkout -- NOMBRE
```

Descartar cambios interativamente (para wip):
```
$ git checkout -p
```

Ir a branch nueva:
```
$ git checkout -b NOMBRE
$ git checkout -b NOMBRE origin/NOMBRE
```

### Branch

Crear branch:
```
$ git branch NOMBRE
```

Crear branch:
```
$ git branch NOMBRE
```

Listar branch:
```
$ git branch
$ git branch -a (todas)
$ git branch -v
```

Listar branch remotas:
```
$ git branch -r
```

Borrar rama:
```
$ git branch -d NOMBRE
```

Borrar rama fusionada:
```
$ git branch -D NOMBRE
```

### Merge

Fusionar: Situarse en la rama que va a fusionar
```
$ git merge NOMBRE
```

Cancelar merge:
```
$ git merge --abort
```

Fusionar sin FF: Situarse en la rama que va a fusionar
```
$ git merge --no-ff NOMBRE
```

### Remote

Agregar un origen:
```
$ git remote add origin RUTA_REMOTA
```

Agregar otro remoto:
```
$ git remote add NOMBRE RUTA_REMOTA
```

Remover remoto:
```
$ git remote rm NOMBRE
```

Mostar un remoto:
```
$ git remote show origin
```

Podar ramas remotas:
```
$ git remote prune origin
```

Listar repos remotos:
```
$ git remote
$ git remote -v
```

### Tag

Listar tags:
```
$ git tag
```

Crear tag (-f forzar):
```
$ git tag VERSION
$ git tag VERSION SHA
$ git tag -a VERSION -m "MENSAJE"
$ git tag -a VERSION -m "MENSAJE" SHA
```

### Fetch

Descargar tags:
```
$ git fetch --tags
```

### Clean

Limpiar repo:
```
$ git clean -f -d
$ git clean -xfd
```

### Satsh

Respaldar cambios en wip (Stash):
```
$ git stash
```

Recuperar cambios del wip:
```
$ git stash pop
```

Limpiar stash:
```
$ git stash clear
```

### Diff

Diff stash:
```
$ git diff stash
$ git diff stash -- ARCHIVO
```

Revisar cambios:
```
$ git diff (para cambios no agregados)
$ git diff ARCHIVO
$ git diff --staged (para cambios agregados)
$ git diff HEAD~NUMERO ARCHIVO
```

Comparación con commit anterior:
```
$ git diff HEAD^ HEAD
$ git diff HEAD^ HEAD ARCHIVO
$ git diff HEAD~NUMERO_MAYOR HEAD~NUMERO_MENOR
$ git diff SHA_ANTERIOR SHA_MAS_RECIENTE
```

### Remove

Remover:
```
$ git rm NOMBRE
$ git rm -r FOLDER
```

### Show

Mostrar commit:
```
$ git show HEAD
$ git show SHA
```

Mostrar un commit anterior:
```
$ git show HEAD^
$ git show HEAD~1
```

Mostrar dos commit anterior:
```
$ git show HEAD^^
$ git show HEAD~2
```

Mostrar varios commit anterior:
```
$ git show HEAD~NUMERO
```

### Patch

Crear patch:
```
$ git format-patch -1
$ git format-patch -1 SHA
$ git format-patch -NUMBER
```

Ver patch:
```
$ git apply --stat ARCHIVO
```

Verificar patch:
```
$ git apply --check ARCHIVO
```

Aplicar patch:
```
$ git apply ARCHIVO
$ git apply -3 ARCHIVO
```

### Rebase

Rebase: Situarse en la rama que va a fusionar
```
$ git rebase BRANCH
```