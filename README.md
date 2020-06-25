### Vous démarrez un projet en équipe? Vous ne savez pas encore comment faire? Nous allons vous présenter l'outil indispensable pour réussir ce premier projet

# Gérer son workflow

## Intro

  Vous avez déjà été plusieurs sur un meme repository à travailler en même temps sur les mêmes fichiers ? Alors vous avez probablement déjà rencontré les conflits de Git, ces petits incrustes qui viennent te casser les pieds et chier sur ton code lorsque vous modifiez le même fichier et que Git ne sait pas quoi garder. Si t'en as jamais vu, déjà tu devrais jouer au lotto mais ça ressemble à ça  (lignes 8 à 12):
  
   ![Exemple de conflit Git](https://www.grandcircus.co/wp-content/uploads/2016/09/9.png)
  
  N'ayez pas peur car dans le cadre de THP, nous avons réalisé cette mission où vous apprendrez à travailler en équipe comme des pros ! Git, git flow et la notion de feature n'auront plus de secret et adieu aux conflits de Git.
  
## Git et Gitflow

  Créé par le créateur de Linux en 2005, Git est un outil puissant de versioning opensource qui présente de nombreux avantages, dont celui de conserver l’intégralité des fichiers à chaque version (et pas seulement les modifications, garantissant ainsi l’intégrité des données), et surtout d’être distribué. Ne nécessitant pas obligatoirement de serveur central, il permet ainsi de travailler localement, hors ligne, et des opérations normalement chronophages et complexes, comme faire des branches, deviennent instantanées.
  
### Quelques fonctionnalités intéressantes de Git
  
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

Ici nous vous montrons l'usage du Git-Flow pour un travail d'équipe mais même dans un projet où vous êtes seul, il est vivement conseillé, car il:

  -permet de mettre en place tout de suite des bonnes pratiques de développement
  -permet de livrer des correctifs en un temps record sans risquer de désorganiser tout le système
  -offre une gestion de son travail extrêmement ordonné et vous fera gagner un temps considérable sur de longs projets
  
Voici un schéma afin de comprendre la notion de feature et le fonctionnement de Git-flow visuellement:
  
![Schéma Gitflow](https://media.discordapp.net/attachments/705675068096905216/725302729433415761/gitflow.png?width=537&height=712)
  
## Utilisation

### Prérequis

  Si vous n'avez pas encore Git il faut l'installer sur votre machine (en passant par le terminal bien sûr) :
    -Pour MacOs : 
      $ brew install git-flow-avh 
    -Pour Linux : 
      $ apt-get install git-flow
    -Pour windows (avec Cygwin, pas dans cmd) : 
      $ wget -q -O - --no-check-certificate https://raw.github.com/petervanderdoes/gitflow-avh/develop/contrib/gitflow-    installer.sh install stable | bash
      
### Initialisation

  Commencez à utiliser git-flow en l'initialisant dans un repo git existant :
    $ git flow init
  Vous devrez répondre à une série de questions sur l'appelation des branches. Personellement, je laisse toutes les valeurs par     défaut et c'est ce que nous vous conseillons.
  
### Démarrer le projet

  Maintenant que ton outil est initialisé chez tous les membres de l'équipe, il ne reste plus qu'à coder. Mais attention on va coder intelligement pour éviter les pertes de temps et de croiser les méchants conflits tout moches. Pour ça chaque membre de l'équipe devra créer une feature (une nouvelle branche) pour chaque, ABSOLUMENT CHAQUE, modification du code / correction de bug / ou ajout d'une fonctionnalité. 
  
Pour créer sa première feature, attention de toujours être sur develop avant de le faire et d'avoir pull la dernière version de develop:

  $ git flow feature start NOM_DE_TA_FEATURE
  
Cette commande copie la branche actuelle, dans une nouvelle branche qui sera "feature/NOM_DE_TA_FEATURE". Maintenant tu peux commencer à bosser, essaie de bosser uniquement sur une fonctionnalité par feature, car si tu fais tout sur la même branche ça rendra inutile l'utilisation du Git-Flow. Une fois que ta fonctionnalité est  finie et fonctionnelle voici la marche à suivre:

  1) $ git add --all
  2) $ git commit -m "Nom de ton commit"
  3) $ git push --set-upstream origin feature/NOM_DE_TA_FEATURE
  4) Rends toi sur la plateforme Github.com, vas sur le repo en question, si tu as bien suivi les étapes précédentes tu devrais voir ça sur la page d'accueil du repo :
  
  ![Pull request](https://i.ytimg.com/vi/rgbCcBNZcdQ/maxresdefault.jpg)
 
   Clique sur "Compare & pull request" il va te proposer de mettre un commentaire à ta feature (mets en un pour expliquer les modifs que tu as fait aux membres de ton équipe) et   poste ta pull request, voici à quoi devrait ressembler ta page :
  
  ![Pull request formulaire](https://sansnom.org/activities/discussions/documentation/free-software/pull-request/pull_request.png)
  
  Tu remarqueras en haut en vert il y a écrit "Able to merge", ça signifie que ta branche n'a aucun conflit avec la branche develop (pas de modifications en commun). Mais il est 
  probable et fréquent que tu tombes sur des conflits, il y aura alors ça sur la page Github de ta pull request
  
  ![Conflits dans une pull request](https://github.blog/wp-content/uploads/2016/12/fd64b010-c06b-11e6-9dd3-a827e299c5bf.gif?fit=1360%2C426)
  

