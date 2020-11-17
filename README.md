Introduction :
===
Qu'est-ce que Git ?

Qu'est-ce que Github ?

Qu'est-ce que Github Project ?

Vous incarnerez 🐒.


Step 0 : Créer le projet
===
🐒 Décide de créer un super site web dont le code source serait hébergé sur Github.

- Créer un *repository* Github. (Readme, gitignore ?)

- Ajouter le code que 🐎 lui a donné directement depuis la page du repository.
 
- Se rendre dans la partie *Projet* et en créer un nouveau. (Template ?)

- Créer des notes / issues (Assignees, Project ...)


Step 1 - Récupérer le repository en local
===
🐒 Est prêt à développer son site, pour ça il décide de *cloner* son projet sur son PC.
<details>
 <summary>Solution</summary>

```console
rafale@workshop:~$ git clone <SSH KEY>
```
</details>


2 - Intéragir avec les modifications apportées au repository
===
🐒 Apporte des modifications à son projet mais a oublié quels fichiers ont été modifiés, il se demande quelle commande pourrait l'aider à s'en rappeler.
<details>
 <summary>Solution</summary>

```console
rafale@workshop:~$ git diff <FILE PATH || SOURCE BRANCH>
```
</details>
🐒 Aimerait maintenant savoir quelles modifications ont été apportées aux fichiers, quelle commande utiliser ?
<details>
 <summary>Solution</summary>

```console
rafale@workshop:~$ git diff <FILE PATH || SOURCE BRANCH>
```
</details>
🐒 N'a plus envie d'apporter des modifications à son README.md, il cherche la commande pour remettre ce fichier à son état d'origine.
<details>
 <summary>Solution</summary>

```console
rafale@workshop:~$ git checkout <FILE PATH>
```
</details>
🐒 Est sous Max OS, un .DS_Store a été crée, il pourrait le supprimer à main mais en tant que bon développeur il se demande comment faire pour que ce fichier n'intéragisse jamais avec git, comment faire ?
<details>
 <summary>Solution</summary>

```console
rafale@workshop:~$ cat .gitignore
```
    /node_modules   #Indique que le dossier node_modules ne sera pas pris en compte par git

    *.log   #Indique que tous les fichiers ayant pour extension .log ne seont pas pris en compte par git
    
    .DS_Store   #Indique que le fichier DS_Store ne sera pas pris en compte par git
</details>


3 - Envoyer des modifications
===
🐒 Est maintenant satisfait de son travail, il aimerait *ajouter* ses fichiers.
<details>
 <summary>Solution</summary>

```console
rafale@workshop:~$ git add <FILE PATH>
rafale@workshop:~$ git add -A
```
</details>
🐒 Se change d'avis et décide de ne plus ajouter ses fichiers.
<details>
 <summary>Solution</summary>

```console
rafale@workshop:~$ git reset <FILE PATH>
rafale@workshop:~$ git reset
```
</details>
🐒 Rechange d'avis, rajoute ses fichiers et décide de les envoyer sur Github. (Commit name)
<details>
 <summary>Solution</summary>

```console
rafale@workshop:~$ git commit -m <COMMIT MESSAGE>
rafale@workshop:~$ git push <BRANCH NAME>
```
</details>


4 - Récupérer des modifications
===
🐒 Décide de modifier son README.md directement depuis la page de son repository sur Github.
Il y apporte aussi des modifications depuis son PC sans les ajouter / commit / push.
Il est satisfait de son README mais aimerait récupérer en local ce qu'il a fait sur Github avant d'ajouter ses fichiers, quelle serait la commande à utiliser ?
<details>
 <summary>Solution</summary>

```console
rafale@workshop:~$ git pull <BRANCH NAME>
```
</details>
🐒 Pense avoir bien fait mais git lui demande de *commit* avant de pourvoir récupérer les modifications, hors il n'a pas envie de commit avant d'avoir récupéré son travail, il décite donc de mettre son travail en local de côté le temps de récupérer son travail en local.
<details>
 <summary>Solution</summary>

```console
rafale@workshop:~$ git stash
rafale@workshop:~$ git pull <BRANCH NAME>
rafale@workshop:~$ git stash pop
```
</details>
🐒 Ne comprend pas ce que git lui demande en parlant de *merge* comment faire en sorte de ne gardes que les modifications effectuées en local ? (Merge ?)
<details>
 <summary>Solution</summary>

    Accept Current Change | Accept Incoming Change | Accept Both Changes | Compare Changes
    # Séléctionner Incoming Change
</details>


5 - Revenir en arrière
===
🐒 Ne se rappelle plus de tout le travail qu'il a fait, il sait qu'une commande git existe pour avoir accès à ses commits mais laquelle ?
<details>
 <summary>Solution</summary>

```console
rafale@workshop:~$ git log
```
</details>
🐒 Est nostalgique et aimerait revenir à l'époque où Diablox9 était plus connu que Kim Glow, il aimerait donc revenir à son premier commit, quelle serait la commande à utiliser ?
<details>
 <summary>Solution</summary>

```console
rafale@workshop:~$ git checkout <COMMIT ID>
rafale@workshop:~$ git switch - #Pour revenir à la dernière version
```
</details>


Step 6 - Travailler avec des branches
===
<details>
 <summary>Solution</summary>

```console
rafale@workshop:~$ git branch
```
</details>

<details>
 <summary>Solution</summary>
 
 ```console
rafale@workshop:~$ git checkout <BRANCH NAME>
```
</details>

<details>
 <summary>Solution</summary>
 
 ```console
rafale@workshop:~$ git fetch
```
</details>

<details>
 <summary>Solution</summary>

```console
rafale@workshop:~$ git merge
```
</details>

<details>
 <summary>Solution</summary>

```console
rafale@workshop:~$ git rebase
```
</details>
