# Workshop_Git-GithubProject

Introduction : 
What is Git ?
What is Github ?
What is Github Project ?

Prérequis:
Un compte Github
Git installé sur le PC

Git :
===
0 - Créer un repository sur Github
---
Un projet sans README est invisible

Nous parlerons du .gitignore dans quelques minutes.

Explorer les différentes lisences.

1 - Récupérer ce repository en local (clone)
---
```console
rafale@workshop:~$ git clone <SSH KEY>
```
2 - Faire des modifications
---
```console
rafale@workshop:~$ git status
```
```console
rafale@workshop:~$ git diff <FILE PATH || SOURCE BRANCH>
```
```console
rafale@workshop:~$ git checkout <FILE PATH>
```
```console
rafale@workshop:~$ cat .gitignore
```
    /node_modules

    *.log
3 - Envoyer des modifications
---
```console
rafale@workshop:~$ git add <FILE PATH>
rafale@workshop:~$ git add -A
```
```console
rafale@workshop:~$ git reset <FILE PATH>
rafale@workshop:~$ git reset
```
```console
rafale@workshop:~$ git commit -m <COMMIT MESSAGE>
```
```console
rafale@workshop:~$ git push <BRANCH NAME>
```
4 - Récupérer des modifications
---
```console
rafale@workshop:~$ git pull <BRANCH NAME>
```
```console
rafale@workshop:~$ git stash
rafale@workshop:~$ git stash pop
```
Comment merge ?

5 - Revenir en arrière (log, checkout)
---
```console
rafale@workshop:~$ git log
```
```console
rafale@workshop:~$ git checkout <COMMIT ID>
```
6 - Travailler avec des branches
---
```console
rafale@workshop:~$ git branch
```
```console
rafale@workshop:~$ git checkout <BRANCH NAME>
```
```console
rafale@workshop:~$ git fetch
```
```console
rafale@workshop:~$ git merge
```
```console
rafale@workshop:~$ git rebase
```
7 - Git flow
---
```console
rafale@workshop:~$ sudo apt-get install git-flow
```
https://danielkummer.github.io/git-flow-cheatsheet/index.fr_FR.html


Github project :
===
1 - Création du projet
---

2 - Créer des Issues
---

3 - Faire une pull request
---
