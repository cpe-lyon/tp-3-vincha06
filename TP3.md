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

### 1


