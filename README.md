<h1 align="center">Welcome to So_Pekocko 👋</h1>
<img src="images/logo.png" alt="logo So Pekocko"/>
<p>
  <img alt="Version" src="https://img.shields.io/badge/version-0.0.0-blue.svg?cacheSeconds=2592000" />
  <a href="https://twitter.com/virgilegug" target="_blank">
    <img alt="Twitter: virgilegug" src="https://img.shields.io/twitter/follow/virgilegug.svg?style=social" />
  </a>
</p>

> Site de notation de sauces

## 🎯 Objectif
* Implémenter un modèle logique de données conformément à la réglementation
* Stocker des données de manière sécurisée
* Mettre en œuvre des opérations CRUD de manière sécurisée

## Install

**FRONTEND**
* Installation des dépendances
```sh
npm install
```
* Lancement du serveur Angular
```sh
ng serve
```

**BACKEND**
* Installation des dépendances
```sh
npm install
```
* Lancement du serveur Node.js
```sh
node server
```

## Documentation API
|Verbe|Paramètres|Corps de la demande (le cas échéant)|Type de réponse attendue|Fonction
|---|---|---|---|---|
|<img alt="POST" src="https://img.shields.io/badge/-POST-blue"/>|/api/auth/signup|{ email: string, password:string }|{ message: string }|Chiffre le mot de passe de l'utilisateur, ajoute l'utilisateur à la base de données|
|<img alt="POST" src="https://img.shields.io/badge/-POST-blue"/>|/api/auth/login|{ email: string, password: string }|{ userId: string, token: string }|Vérifie les informations d'identification de l'utilisateur, en renvoyant l'identifiant userID depuis la base de données et un jeton Web JSON signé(contenant également l'identifiant userID)
|<img alt="GET" src="https://img.shields.io/badge/-GET-blue"/>|/api/sauces|_|Tableau des sauces|Renvoie le tableau de toutes les sauces dans la base de données|
|<img alt="GET" src="https://img.shields.io/badge/-GET-blue"/>|/api/sauces/:id|_|Sauce unique|Renvoie la sauce avec l'ID fourni|
|<img alt="POST" src="https://img.shields.io/badge/-POST-blue"/>|/api/sauces|{ sauce: Chaîne, image: Fichier }|{ message: Chaîne }|Capture et enregistre l'image, analyse la sauce en utilisant une chaîne de caractères et l'enregistre dans la base de données, en définissant correctement son image URL. Remet les sauces aimées et cellesdétestées à 0, et les sauces usersliked et celles usersdisliked aux tableaux vides.|
|<img alt="PUT" src="https://img.shields.io/badge/-PUT-blue"/>|/api/sauces/:id|SOIT Sauce comme JSON OU { sauce:Chaîne, image: Fichier }|{ message: Chaîne }|Met à jour la sauce avec l'identifiant fourni. Si une image est téléchargée, capturez-la et mettez à jour l'image URL des sauces. Si aucun fichier n'est fourni, les détails de la sauce figurent directement dans le corps de la demande(req.body.name, req.body.heat etc). Si un fichier est fourni, la sauce avec chaîne est en req.body.sauce.|
|<img alt="DELETE" src="https://img.shields.io/badge/-DELETE-blue"/>|/api/sauces/:id|_|{ message: Chaîne }|Supprime la sauce avec l'ID fourni.|
|<img alt="POST" src="https://img.shields.io/badge/-POST-blue"/>|/api/sauces/:id/like|{ userId: Chaîne, j'aime :Nombre }|{ message: Chaîne }|Définit le statut"j'aime" pour userID fourni. Si j'aime = 1, l'utilisateur aime la sauce. Si j'aime = 0, l'utilisateur annule ce qu'il aime ou ce qu'il n'aime pas. Si j'aime = -1, l'utilisateur n'aime pas la sauce. L'identifiant de l'utilisateur doit être ajouté ou supprimé du tableau approprié, en gardant une trace de ses préférences et en l'empêchant d'aimer ou de ne pas aimer la même sauce plusieurs fois. Nombre total de "j'aime" et de "je n'aime pas" à mettre à jour avec chaque "j'aime".|

## Author
👤 **Virgile Guglielmi**

* Twitter: [@virgilegug](https://twitter.com/virgilegug)
* Github: [@VGMSoft](https://github.com/VGMSoft)

## Show your support

Give a ⭐️ if this project helped you!

***
_This README was generated by [readme-md-generator](https://github.com/kefranabg/readme-md-generator)_
