# redirection_url

Transformer des urls dans un pattern "item-iddelurlinsere", et y avoir accès à l'url en rentrant le pattern dans l'url exemple "votreapp/pattern"

technologies: node.js, express, ejs, mongodb, orm --> mongoose, module : express-paginate, module qrcode

structure mvc

solutions :

pour pouvoir enregistrer le pattern j'ai concaténé "item-" avec l'id de l'url dans la propriété nom de la classe ObjectId dans la fonction save du controller dédié.

pour pouvoir accéder à l'url du site en utilisant le "pattern+id" dans la route, j'ai du faire passer une paramètre item dans la route redirection pour la rendre dynamique, ce paramètre permet de récupérer le "/pattern+id" entré dans le navigateur grace à la fonction redirection. 

La fonction utilise ce paramètre dan le find one de la collection urls pour récupérer l'url associée et y être redirigé.
Pour aller plus loin je pourrais afficher la liste des items générés accompagnés des url des sites.

Une fois les url listés le lien ouvre une fenêtre modale au clique grâce à un modal bootstrap. Une requête ajax récupère les données du qr code au niveau du back pour les ramener vers le front et permettre de changer la source de l'image contenue dans la fenêtre modale en direct.
