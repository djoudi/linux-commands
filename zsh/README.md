# Configuración de **zsh** (ubuntu 18.04)

### Prerequisitos

```
# apt install zsh vim git curl wget
```

### Instalar [oh my zsh](https://ohmyz.sh/)

```
$ sh -c "$(curl -fsSL https://raw.github.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
```

actualizar el shell a zsh:

```
# chsh -s `which zsh`
```

y cerrar/iniciar sesión:

```
$ pkill -KILL -u $USER
```

### Temas

#### Actualizar tema a [agnoster](https://github.com/agnoster/agnoster-zsh-theme)

instalar fuentes ([aquí](https://powerline.readthedocs.io/en/latest/installation/linux.html#fonts-installation)):

```
# apt install fonts-powerline
```

abrir archivo de configuración:

```
$ vi ~/.zshrc    
```

actualizar tema:

```
ZSH_THEME="agnoster"
```

#### Instalar [powerlevel9k](https://github.com/bhilburn/powerlevel9k)

```
$ git clone https://github.com/bhilburn/powerlevel9k.git ~/.oh-my-zsh/custom/themes/powerlevel9k
```

abrir archivo de configuración:

```
$ vi ~/.zshrc    
```

actualizar tema:

```
ZSH_THEME="powerlevel9k/powerlevel9k"
```

agregar configuraciones:

```
POWERLEVEL9K_LEFT_PROMPT_ELEMENTS=(context dir newline vcs)
POWERLEVEL9K_RIGHT_PROMPT_ELEMENTS=(status ram time)
```

### Otros

- [Cheat sheet](https://github.com/robbyrussell/oh-my-zsh/wiki/Cheatsheet)
