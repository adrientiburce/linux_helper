# Astuces Linux 

## Terminal : Zsh 

1) Installation de *Zsh*

```
sudo apt install zsh
```

2) Installation de **Oh-my-zsh**
```
sh -c "$(curl -fsSL https://raw.github.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
```
3) On peut changer de **thème** : 

- Changer la ligne 11 du fichier `~/.zshrc` 
- Chosir un thème disponible [ici](https://github.com/robbyrussell/oh-my-zsh/wiki/Themes)

4) Astuces pour git avec zsh : 
Si l'on veut ne pas avoir de sortie lorsque l'on tape `git branch` ou `git log` :
```
git config --global core.pager ''
```

5) Avoir zsh par **défaut** : 
```
chsh -s $(which zsh)
```
6) Une auto-complétion sympa : 
Ajouter la ligne suivante à votre `.zshrc` ( ou ajoute une option avec la commande `setopt`) 
```
setopt correct
```
- désormains pour accéder à `Document/info` ou peut simplement taper : `cd ~/D/i` 