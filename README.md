Vous incarnerez 🐒.


Step 0 : Créer le projet
===
🐒 Décide de créer un super site web dont le code source serait hébergé sur Github.

- Créer un *repository* Github.
> Le README est le fichier le plus important d'un repository public, il permet aux personnes intéressées par le projet de savoir en quoi il consiste, comment l'utiliser ou d'obtenir d'autres informations concernant ce projet. 

- Ajouter [le code](https://github.com/RaphaelDk/Workshop_Git-GithubProject/blob/main/index.html) que 🐎 vous a donné directement depuis la page du repository.
 
- Se rendre dans la partie *Projet* et en créer un nouveau.
> Nous utiliserons pour ce workshop le template **Automated kanban**, il permet d'automatiquement passer à *done* les issues liées à des pull requests terminées, nous y reviendrons plus tard.

- Créer des issues représentant des fonctionnalités que 🐒 aimerait intégrer au projet.
> Une note n'existe que dans la partie *Projects* d'un repository à la différence d'une issue qui sera visible directement dans la partie *Issues* qui contient toutes les corrections ou feature que le développeur ajoutera à son projet.

> Les issues que vous créerez vous seront assignées, auront les tags associés et seront dans la colonne du projet qui correspond à leur état.


Step 1 - Récupérer le repository en local
===
🐒 Est prêt à développer son site, pour ça il décide de *cloner* son projet sur son PC.
<details>
 <summary>Solution</summary>

```console
rafale@workshop:~$ git clone <SSH KEY>
```
</details>


Step 2 - Intéragir avec les modifications apportées au repository
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

🐒 A apporté des modifications à son README.md mais change d'avis, il cherche la commande pour remettre ce fichier à son état d'origine.
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


Step 3 - Envoyer des modifications
===

🐒 Est maintenant satisfait de son travail, il aimerait *ajouter* ses fichiers.
<details>
 <summary>Solution</summary>

```console
rafale@workshop:~$ git add <FILE PATH>
rafale@workshop:~$ git add -A
```
</details>

🐒 Change d'avis et décide de ne plus ajouter ses fichiers.
<details>
 <summary>Solution</summary>

```console
rafale@workshop:~$ git reset <FILE PATH>
rafale@workshop:~$ git reset
```
</details>

🐒 Rechange d'avis, rajoute ses fichiers et décide de les envoyer sur Github.

> Un message de commit doit être une courte phrase résumant ce qui a était fait, s'il est trop long c'est qu'il aurait du être fait plus tot.
<details>
 <summary>Solution</summary>

```console
rafale@workshop:~$ git commit -m <COMMIT MESSAGE>
rafale@workshop:~$ git push <BRANCH NAME>
```
</details>

>🐒 A donc push sa première feature, il décide donc de remettre à jour son état sur le projet à la main car ce n'est pas encore fait automatiquement.


Step 4 - Récupérer des modifications
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

🐒 Pense avoir bien fait mais git lui demande de commit avant de pourvoir récupérer les modifications, hors il n'a pas envie de commit avant d'avoir récupéré son travail, il décite donc de mettre son travail en local de côté le temps de récupérer son travail en local.
<details>
 <summary>Solution</summary>

```console
rafale@workshop:~$ git stash
rafale@workshop:~$ git pull <BRANCH NAME>
rafale@workshop:~$ git stash pop
```
</details>

🐒 Ne comprend pas ce que git lui demande en parlant de merge comment faire en sorte de ne garder que les modifications effectuées en local ?
<details>
 <summary>Solution</summary>

    Accept Current Change | Accept Incoming Change | Accept Both Changes | Compare Changes
    # Sélectionner Incoming Change
</details>


Step 5 - Revenir en arrière
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

🐎 A parlé à 🐒 d'une meilleure pratique concernant l'utilisation de branches, il décide donc de lire [cette documentation](https://danielkummer.github.io/git-flow-cheatsheet/index.fr_FR.html).

🐒 A donc envie d'essayer cette nouvelle façon de travailler avec git sans installer git-flow, pour ça la première étape est de créer la branche develop.
<details>
 <summary>Solution</summary>

```console
rafale@workshop:~$ git branch -b develop && git checkout develop
rafale@workshop:~$ git checkout -b develop # Manière plus simple de le faire
```
</details>

🐒 A bien créé sa branche mais elle n'apparait pas sur le Github, comment expliquer cela ?
<details>
 <summary>Solution</summary>
 🐒 N'a créé sa branche qu'en local, elle n'apparaitra pas sur le serveur avant qu'elle n'ait été push.
 
 Il se peut que 🐎 qui ait déja cloné le repository n'ait pas accès à cette branche même après un push de 🐒, il devra pour la voir exécuter la commande :

```console
rafale@workshop:~$ git fetch
```
</details>

🐒 A ensuite créé une branche pour sa nouvelle feature mais après l'avoir quasiment terminé il se rend compte qu'il aurait besoin de ce que 🐎 a push sur develop pour qu'elle soit totalement terminée, il aimerait donc amener les modifications faites sur develop dans sa branche.

🐎 Lui avait justement envoyé [une documentation](https://www.atlassian.com/fr/git/tutorials/merging-vs-rebasing) à ce sujet, il décide donc d'en prendre connaissance et d'essayer les deux méthodes décrites.
<details>
 <summary>Solution</summary>

```console
rafale@workshop:~$ man git-merge
rafale@workshop:~$ man git-rebase
```
</details>

🐒 A donc une branche à jour avec develop et aimerait maintenant mettre sa nouvelle feature sur develop, pour ça il se rend dans la partie *Pull requests* de son repository pour en créer une.

🐒 Voit qu'il pourrait lier cette Pull request à son projet mais il décide de ne pas le faire car il y a déja une issue dans ce projet qui détaille ce qui a été fait dans cette PR.

Après avoir vérifié son code sur cette PR, 🐒 n'est pas satisfait d'une des lignes de son code, il décide donc d'y mettre un commentaire depuis Github.

Après avoir résolu ce problème, 🐒 est satisfait de son travail et décide de merge cette PR, il est content car l'issue liée est directement passée à done.
