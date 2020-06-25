### Vous démarrez un projet en équipe? Vous ne savez pas encore comment faire? Nous allons vous présenter l'outil indispensable pour réussir ce premier projet

# Gerer son workflow

## Intro

  Vous avez déjà été plusieurs sur un meme repository à travailler en même temps sur les mêmes fichiers ? Alors vous avez probablement déjà rencontré les conflits de Git, ces petits incrustes qui viennent te casser les pieds et chier sur ton code lorsque vous modifiez le même fichier et que Git ne sait pas quoi garder. Si t'en as jamais vu, déjà tu devrais jouer au lotto mais ça ressemble à ça  (lignes 8 à 12):
  
   ![Exemple de conflit Git](https://www.grandcircus.co/wp-content/uploads/2016/09/9.png)
  
  N'ayez pas peur car dans le cadre de THP, nous avons réalisé cette mission où vous apprendrez à travailler en équipe comme des pros ! Git, git flow et la notion de feature n'auront plus de secret et adieu aux conflits de Git.
  
## Git et Gitflow

  Créé par le créateur de Linux en 2005, Git est un outil puissant de versioning opensource qui présente de nombreux avantages, dont celui de conserver l’intégralité des fichiers à chaque version (et pas seulement les modifications, garantissant ainsi l’intégrité des données), et surtout d’être distribué. Ne nécessitant pas obligatoirement de serveur central, il permet ainsi de travailler localement, hors ligne, et des opérations normalement chronophages et complexes, comme faire des branches, deviennent instantanées.
  
### Quelques fonctionnalités intéressantes
  
  -Un repo (raccourci de repository) git est toujours cloné entièrement, permettant ainsi un accès à tout l’historique.
  -La sauvegarde se fait en 3 étapes, les fichiers passant par 3 états:
    1)Modified : le fichier est détecté comme ayant des modifications par rapport à sa sauvegarde précédente.
    2)Staged : le fichier est “mis à l’index” dans l’aire de “staging” et donc comme faisant partie du prochain commit.
    3)Committed : le fichier modifié est enregistré dans la chaîne de commits.
   -Il est possible de dire à Git d’ignorer certains fichiers (.gitignore). C’est particulièrement important à propos de certaines    données qui ne    doivent jamais apparaître dans le dépôt, comme les fichiers qui contiennent les mots de passe et les données    environnementales.
   
### Git-Flow

  Le git flow est une très bonne pratique, il permet de travailler efficacement, avec la notion de feature, branches. Chaque branche est une partie d'un même repo, comme un arbre qui aurait un tronc puis pleins de petites branches toutes différentes mais partant généralement du même tronc. Exemples:
  
  -La branche "master", sera la branche du rendu final de votre projet (/!\ On ne push jamais un test ou une toute nouvelle         feature dessus /!\)
  -La branche "develop" est la branche principale du développement de votre projet (votre tronc d'arbre pour tout ce qui est dev      de votre app)
  -Les branches de “feature/” permettent de développer les fonctionnalités souhaitées
  -La branche “release” est dédiée aux pré-livraisons et permet de tester si tout est OK
  -La branche “hotfix” est dédiée aux corrections urgentes

Ici nous vous montrons l'usage du Git-Flow pour un travail d'équipe mais même dans un projet où vous êtes seul, il est vivement conseillé, car il:

  -permet de mettre en place tout de suite des bonnes pratiques de développement
  -permet de livrer des correctifs en un temps record sans risquer de désorganiser tout le système
  -offre une gestion de son travail extrêmement ordonné et vous fera gagner un temps considérable sur de longs projets
  
Voici un schéma afin de comprendre la notion de feature et le fonctionnement de Git-flow visuellement:
  
![Schéma Gitflow](https://media.discordapp.net/attachments/705675068096905216/725302729433415761/gitflow.png?width=537&height=712)
  

