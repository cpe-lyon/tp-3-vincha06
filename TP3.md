Vincent CHAVES - 3ICS

# TP 3 - Utilisateurs, groupes et permissions

## Exercice 1.  Gestion des utilisateurs et des groupes

### 1. Utilisez la commande groupadd pour créer deux groupes dev et infra
- ![image](https://user-images.githubusercontent.com/113091304/191703714-3a713246-431b-461d-8dc3-a60e672b2cf0.png)

### 2. Créez ensuite 4 utilisateurs alice, bob, charlie, dave avec la commande useradd, en demandant la création de leur dossier personnel et avec bash pour shell
- ![image](https://user-images.githubusercontent.com/113091304/191705567-40241e09-37e5-422f-9bec-f84fd8cbb3a2.png)

### 3. Ajoutez les utilisateurs dans les groupes créés :
###     - alice, bob, dave dans dev
###     - bob, charlie, dave dans infra
- ![image](https://user-images.githubusercontent.com/113091304/191707543-ddecf4eb-61ed-495c-be2c-ce0d4d345910.png)

### 4. Donnez deux moyens d’afficher les membres de infra
- ![image](https://user-images.githubusercontent.com/113091304/191709568-b5a763ea-bb57-447e-918f-26e512f6a2b5.png)
- ![image](https://user-images.githubusercontent.com/113091304/191709727-4f255611-d5f1-40a3-b555-77198237505e.png)
- On peut aussi aller dans /home puis effectuer un "ll"

### 5. Faites de dev le groupe propriétaire des répertoires /home/alice et /home/bob et de infra le groupe propriétaire de /home/charlie et /home/dave
- ![image](https://user-images.githubusercontent.com/113091304/191714057-6ee7c9e1-7fe2-4386-8738-1895b7227306.png)

### 6. Remplacez le groupe primaire des utilisateurs :
###   - dev pour alice et bob
###   - infra pour charlie et dave
![image](https://user-images.githubusercontent.com/113091304/191715897-c84525bb-6e4d-4045-b6b8-7ee4a1c2f347.png)

### 7. Créez deux répertoires /home/dev et /home/infra pour le contenu commun aux membres de chaque groupe, et mettez en place les permissions leur permettant d’écrire dans ces dossiers.
- ![image](https://user-images.githubusercontent.com/113091304/192102489-a6301ddd-dd50-4408-bffe-1dd5fd6140b5.png)
- ![image](https://user-images.githubusercontent.com/113091304/192102510-7c45a9d3-a00c-4732-9381-9d6516e3c94f.png)
- ![image](https://user-images.githubusercontent.com/113091304/192105222-207ec1d8-a0de-404c-8b4e-79b1de96e352.png)

### 8. Comment faire pour que, dans ces dossiers, seul le propriétaire d’un fichier ait le droit de renommer ou supprimer ce fichier ?


### 9. Pouvez-vous ouvrir une session en tant que alice ? Pourquoi ?
- Non car le mot de passe n'a pas été mis en place

### 10. Activez le compte de l’utilisateur alice et vérifiez que vous pouvez désormais vous connecter avec son compte.
- <code>sudo passwd alice</code>
- Ça marche : ![image](https://user-images.githubusercontent.com/113091304/192163047-9d0aa287-0f11-4af5-b81c-b7d657db1f99.png)

### 11. Comment obtenir l’uid et le gid de alice ?
- ![image](https://user-images.githubusercontent.com/113091304/192163104-acff9fc4-427d-4d19-a4a2-f01a8271bdfe.png)

### 12. Quelle commande permet de retrouver l’utilisateur dont l’uid est 1003 ?
- ![image](https://user-images.githubusercontent.com/113091304/192163247-a5722a0d-8a0c-453c-b682-1894092f3cfd.png)

### 13. Quel est l’id du groupe dev ?
- 1002
- ![image](https://user-images.githubusercontent.com/113091304/192163423-4272ae6d-91c7-476b-9870-762e889dc972.png)

### 14. Quel groupe a pour gid 1002 ? ( Rien n’empêche d’avoir un groupe dont le nom serait 1002...)
- dev

### 15. Retirez l’utilisateur charlie du groupe infra. Que se passe-t-il ? Expliquez.
![image](https://user-images.githubusercontent.com/113091304/192163762-195d954b-272a-40dd-bc8c-49369aa3c24a.png) 
- Il s'affiche un message disant que l'utilisateur charlie est retiré du groupe infra.

### 16. Modifiez le compte de dave de sorte que :
#### — il expire au 1er juin 2021
  - J'ai mis au 1er juin 2022 vu que 2021 est déjà passé :
  - ![image](https://user-images.githubusercontent.com/113091304/192164959-63244479-bd5f-468c-9d11-ddd82ea51aaf.png)
#### — il faut changer de mot de passe avant 90 jours
  - ![image](https://user-images.githubusercontent.com/113091304/192166557-6a2ff846-ecc5-4fdd-b00c-bfee9e6492ac.png)
#### — il faut attendre 5 jours pour modifier un mot de passe
  - ![image](https://user-images.githubusercontent.com/113091304/192166570-964e32e4-288a-4b1b-a2f0-f04209d02552.png)
#### — l’utilisateur est averti 14 jours avant l’expiration de son mot de passe
  - ![image](https://user-images.githubusercontent.com/113091304/192166616-0f55d5e3-2ff0-4349-9f25-557319500ba8.png)

#### — le compte sera bloqué 30 jours après expiration du mot de passe
  - ![image](https://user-images.githubusercontent.com/113091304/192166728-9e2c5621-88d9-4c0b-81d4-ade1d93208e6.png)
  
- On vérifie tout ça :
- ![image](https://user-images.githubusercontent.com/113091304/192166763-5e3df689-8849-41e7-ab8f-b8df4e84b03d.png)

### 17. Quel est l’interpréteur de commandes (Shell) de l’utilisateur root ?
- ![image](https://user-images.githubusercontent.com/113091304/192166908-3d9562cb-760b-4aa9-80e8-ad29ef7b7eae.png)
- Le shell de root est donc bash.

### 18. Si vous regardez la liste des comptes présents sur la machine, vous verrez qu’il en existe un nommé nobody. A quoi correspond-il ?
- ![image](https://user-images.githubusercontent.com/113091304/192167223-85d5366c-fcd7-4c53-a3a1-f8dc029e5870.png)
- "nobody" est le nom conventionnel d'un compte d'utilisateur à qui aucun fichier n'appartient, qui n'est dans aucun groupe qui a des privilèges et dont les seules possibilités sont celles que tous les "autres utilisateurs" ont. Il est courant de lancer des démons en tant que nobody, spécialement pour des serveurs, de façon à limiter les dommages qui pourrait être occasionnés par un utilisateur malicieux qui aurait réussi à prendre leur contrôle. 

### 19. Par défaut, combien de temps la commande sudo conserve-t-elle votre mot de passe en mémoire ? Quelle commande permet de forcer sudo à oublier votre mot de passe ?
- Elle conserve le mot de passe en mémoire pendant 15 minutes.
- Pour forcer sudo à oublier le mot de passe, il y a la commande :
- <code> sudo -k </code>

## Exercice 2. Gestion des permissions

### 1. Dans votre $HOME, créez un dossier test, et dans ce dossier un fichier fichier contenant quelques lignes de texte. Quels sont les droits sur test et fichier ?
- ![image](https://user-images.githubusercontent.com/113091304/192206680-da7c8983-26af-4416-b976-2593a40a2bfd.png)
- Les droits sur test sont drwxrwxr-x, donc tout sauf l'écriture des autres, et les droits sur fichier sont -rw-rw-r--, donc lecture et écriture de l'utilisateur, lecture et écriture du groupe, et juste lecture des autres.

### 2. Retirez tous les droits sur ce fichier (même pour vous), puis essayez de le modifier et de l’afficher en tant que root. Conclusion ?
- ![image](https://user-images.githubusercontent.com/113091304/192208089-e3727124-439d-47af-bac3-b7a070b3844d.png)
- ![image](https://user-images.githubusercontent.com/113091304/192208160-dafc7d22-a539-4f94-b117-ac052415b984.png)
> ![image](https://user-images.githubusercontent.com/113091304/192208480-7d5da36e-3137-4fd4-8d53-a5386f3f0edb.png)
- ![image](https://user-images.githubusercontent.com/113091304/192208217-d9ac32c9-7e03-48d9-b292-326f940e0baa.png)
- On ne peut plus accéder au dossier test, par contre le root le peut toujours.
- Conclusion : le root a toujours accès aux dossiers/fichiers même si toutes les permissions sont retirés sur eux.

### 3. Redonnez vous les droits en écriture et exécution sur fichier puis exécutez la commande echo "echo Hello" > fichier. On a vu lors des TP précédents que cette commande remplace le contenu d’un fichier s’il existe déjà. Que peut-on dire au sujet des droits ?
- Je me redonne les droits :
- ![image](https://user-images.githubusercontent.com/113091304/192209727-f1038954-2fda-4dab-826c-273e093fb40e.png)
- ![image](https://user-images.githubusercontent.com/113091304/192209773-27a72b55-c917-40f5-b302-a6e55c97cd97.png)
- Je vérifie si j'ai bien accès à fichier :
- ![image](https://user-images.githubusercontent.com/113091304/192209843-027cc64e-135f-4158-88a2-865e7c8f017b.png)
- Je fais le echo hello :
- ![image](https://user-images.githubusercontent.com/113091304/192210143-03b71f4c-2caa-4332-85ce-f44dcc439493.png)
- Je vérifie les droits :
> ![image](https://user-images.githubusercontent.com/113091304/192210259-d21b23a5-d5bf-470f-ae25-1068eb8e6903.png)
- Je peux donc à nouveau modifier fichier sans les droits root.


### 4. Essayez d’exécuter le fichier. Est-ce que cela fonctionne ? Et avec sudo ? Expliquez.
- Cela marche car l'on vient de se redonner les droits.

### 5. Placez-vous dans le répertoire test, et retirez-vous le droit en lecture pour ce répertoire. Listez le contenu du répertoire, puis exécutez ou affichez le contenu du fichier fichier. Qu’en déduisez-vous ? Rétablissez le droit en lecture sur test.
- Je m'enlève le droit de lecture: 
- ![image](https://user-images.githubusercontent.com/113091304/192211738-a6823b76-de19-4172-876b-4945d2f533ad.png)
- Je tente d'afficher le contenu du répertoire :
- ![image](https://user-images.githubusercontent.com/113091304/192211907-cee82d03-125e-4e1f-82c3-62ea0d0a63de.png)
- Je modifie le fichier puis je le supprime (ça marche) :
- ![image](https://user-images.githubusercontent.com/113091304/192212722-662a1dfd-d6c4-4519-a809-ff3c76e5a48a.png)
- J'en déduis que le droit d'écriture n'a pas été retiré, mais le droit de lecture si.


### 6. Créez dans test un fichier nouveau ainsi qu’un répertoire sstest. Retirez au fichier nouveau et au répertoire test le droit en écriture. Tentez de modifier le fichier nouveau. Rétablissez ensuite le droit en écriture au répertoire test. Tentez de modifier le fichier nouveau, puis de le supprimer. Que pouvezvous déduire de toutes ces manipulations ?
- ![image](https://user-images.githubusercontent.com/113091304/192214496-e65c88cf-5534-4b1b-a033-c2d8e07c8384.png)
- Je ne peux pas écrire dans nouveau par contre je peux le supprimer. Cela veut dire que retirer le droit d'écriture ne retire pas le droit de suppression.

### 7. Positionnez vous dans votre répertoire personnel, puis retirez le droit en exécution du répertoire test. Tentez de créer, supprimer, ou modifier un fichier dans le répertoire test, de vous y déplacer, d’en lister le contenu, etc…Qu’en déduisez vous quant au sens du droit en exécution pour les répertoires ?
- ![image](https://user-images.githubusercontent.com/113091304/192215733-1d994cc5-2abe-4ace-89dc-4fba3a2c97a1.png)
- Rien de tout ça ne marche, retirer le droit d'éxecution nous empêche d'effectuer ces actions.

### 8. Rétablissez le droit en exécution du répertoire test. Positionnez vous dans ce répertoire et retirez lui à nouveau le droit d’exécution. Essayez de créer, supprimer et modifier un fichier dans le répertoire test, de vous déplacer dans ssrep, de lister son contenu. Qu’en concluez-vous quant à l’influence des droits que l’on possède sur le répertoire courant ? Peut-on retourner dans le répertoire parent avec ”cd ..” ? Pouvez-vous donner une explication ?
- Comme pour la question précédente, ça ne marche pas non plus, même si on est déjà dans le répertoire.

### 9. Rétablissez le droit en exécution du répertoire test. Attribuez au fichier fichier les droits suffisants pour qu’une autre personne de votre groupe puisse y accéder en lecture, mais pas en écriture.
- ![image](https://user-images.githubusercontent.com/113091304/192220984-7d97b1a5-667a-4b7f-a533-e39b245db0aa.png)
- Je vérifie avec <code>ll</code>: 
- ![image](https://user-images.githubusercontent.com/113091304/192221124-9dbfcd72-ef4e-4a0f-955e-2098409b8517.png)
- C'est bon. 

### 10. Définissez un umask très restrictif qui interdit à quiconque à part vous l’accès en lecture ou en écriture, ainsi que la traversée de vos répertoires. Testez sur un nouveau fichier et un nouveau répertoire.
- <code>umask 077</code> :
- ![image](https://user-images.githubusercontent.com/113091304/192234796-e6973ce6-941b-44da-a948-73dc114876c0.png)

### 11. Définissez un umask très permissif qui autorise tout le monde à lire vos fichiers et traverser vos répertoires, mais n’autorise que vous à écrire. Testez sur un nouveau fichier et un nouveau répertoire.
- <code>umask 022</code> :
- ![image](https://user-images.githubusercontent.com/113091304/192235203-bb11bebe-3254-4fb8-9658-075b6924a446.png)

### 12. Définissez un umask équilibré qui vous autorise un accès complet et autorise un accès en lecture aux membres de votre groupe. Testez sur un nouveau fichier et un nouveau répertoire.
- <code>umask 037</code> :
- ![image](https://user-images.githubusercontent.com/113091304/192236353-3d4fe27b-72de-46ed-ba7e-18f249b4ffc2.png)

### 13. Transcrivez les commandes suivantes de la notation classique à la notation octale ou vice-versa (vous pourrez vous aider de la commande stat pour valider vos réponses) :
#### - chmod u=rx,g=wx,o=r fic
- <code>chmod 534 fic</code>

#### - chmod uo+w,g-rx fic en sachant que les droits initiaux de fic sont r--r-x---
- Résultat : rw-----w-
- Donc commande : <code>chmod 602 fic</code>

#### - chmod 653 fic en sachant que les droits initiaux de fic sont 711
- 711 = rwx--x--x
- 653 = rw-r-x-wx
- Donc : <code>chmod u-x,g+r,o+w fic</code>
- Ou : <code>chmod u=rw,g=rx,o=wx fic</code>

#### - chmod u+x,g=w,o-r fic en sachant que les droits initiaux de fic sont r--r-x---
- Résultat : r-x-w----
- Donc : <code>chmod 520 fic</code>

### 14. Affichez les droits sur le programme passwd. Que remarquez-vous ? En affichant les droits du fichier /etc/passwd, pouvez-vous justifier les permissions sur le programme passwd ?
- <code>ll /etc</code> :
- ![image](https://user-images.githubusercontent.com/113091304/192241129-9b9b6733-70e1-4810-94ce-d45f83e6e95c.png)
- ou : <code>stat /etc/passwd</code>
- ![image](https://user-images.githubusercontent.com/113091304/192241483-17a24017-a50e-4ba0-8df2-97237a649314.png)
- Seul l'utilisateur a le droit d'écrire le fichier, et seul le root a le droit de l'éxecuter, ce qui est logique à des fins de sécurité.





