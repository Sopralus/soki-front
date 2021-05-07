# soki-front
 
La partie front comprend aussi du back (pour le stream) car nous 
n'avons pas eu assez de temps pour tout séparer sans avoir de 
problèmes.

Le fichier d'index se trouve dans rtmp/index.html.

Dans cette partie nous traitons les sockets côté client.
Nous avons mis en place un système de "rooms" (channels ?)
qui permet de discuter sur plusieurs chat différents.

Nous n'avons pas automatisé les chats selon les streamers 
car nous n'avons pas eu le temps de gérer les channels
de stream.

Les différents chats sont alors en dur dans le html.


Concernant le stream :
Un npm install est nécessaire dans le rep /auth pour que les
streams fonctionnent.
il y a un fichier conf dans /rtmp qui permet de gérer 
la vidéo et sa création. 
les vidéos sont envoyées dans un dossier /data et des extraits
de la vidéo sont stockées pour revenir en arrière pendant le stream

Pour streamer il faut :
Lancer docker depuis la racine.
- serveur : rtmp://localhost:1935/live
- clef : room[numero]?key=supersecret
Etant donné qu'il existe 5 channels codés en dur, on peut donc stream
avec la clef room1?key=supersecret
Notre objectif était de créer les channels selon les streams en cours 
et faire une vérification avec une "streamkey" enregistrée en BDD
mais nous n'avons pas réussi / eu le temps

Ce qu'on peut faire :
- streamer une vidéo sur un channel prédéfini
- regarder la vidéo et envoyer des messages 
- changer de "channel" et accéder à un nouveau chat
- se connecter / s'inscrire
- envoyer des messages même si on n'est pas connectés
