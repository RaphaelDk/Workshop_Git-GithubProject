# Workshop_Git-GithubProject

Introduction : 
What is Git ?

What is Github ?

What is Github Project ?

Par groupe de deux : (dev1) (dev2)

Step 0 : Initialisation du projet
===
- Create a repository -> README important
- Create a project
- Create issues / notes


Step 1 - Récupérer le repository en local
===
Afin d'apporter des modifications au projet, il est nécessaire de le *cloner*
```console
rafale@workshop:~$ git clone <SSH KEY>
``` 

2 - Intéragir avec les modifications apportées au repository
===
(dev1 & dev2) Créent leur fichier et ajoutent une ligne au README
Quelles modifications ont été apportées ?
```console
rafale@workshop:~$ git status
rafale@workshop:~$ git diff <FILE PATH || SOURCE BRANCH>
```
(dev1 & dev2) Se rendent compte qu'ils ne veulement plus modifier le README, comment le faire revenir à son état d'origine ? (via git)
```console
rafale@workshop:~$ git checkout <FILE PATH>
```
Un fichier indésirable se crée lors qu'on exécute le programme, comment faire en sorte de ne pas risquer de le push ?
```console
rafale@workshop:~$ cat .gitignore
```
    /node_modules   #Indique que le dossier node_modules ne sera pas pris en compte par git

    *.log   #Indique que tous les fichiers ayant pour extension .log ne seont pas pris en compte par git
    
    rafale.txt   #Indique que le fichier rafale.txt ne sera pas pris en compte par git

3 - Envoyer des modifications
===
(dev1 & dev2) décident d'*ajouter* les modifications
```console
rafale@workshop:~$ git add <FILE PATH>
rafale@workshop:~$ git add -A
```

(dev1 & dev2) se rend compte qu'il a ajouté un fichier indésirable, mais il ne veut plus les ajouter
```console
rafale@workshop:~$ git reset <FILE PATH>
rafale@workshop:~$ git reset
```

(dev1) décide de *commit* et *push* ses modifications
```console
rafale@workshop:~$ git commit -m <COMMIT MESSAGE>
rafale@workshop:~$ git push <BRANCH NAME>
```

4 - Récupérer des modifications
---
(dev2) décide de récupérer les modifications de (dev1)
```console
rafale@workshop:~$ git pull <BRANCH NAME>
```
Mais git lui demande de *commit* avant, hors il aimerait pouvoir récupérer ce qu'à fait (dev1) avant de commit
```console
rafale@workshop:~$ git stash
rafale@workshop:~$ git pull <BRANCH NAME>
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
