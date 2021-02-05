## Les commandes Linux utilisées au quotidien

`apt update` - Récupére la list des packages à mettre a jour

`apt upgrade` - Met à jour les packages

`apt remove` - Supprime un package

`apt purge` - Supprime un package et les fichier de configuration

`arch` - Determine l'achitecture de votre machine `x64,x32,arm...`

`man` - Donne une description de toute commande linux comme celle-ci :`man ls` . man suivie de la commande souhaiter

`mv` - Déplace ou renomme un fichier/dossier

`pwd` - Affiche l’emplacement ou on se situe

`chmod` - Modifier les permissions d'accès aux fichiers/dossiers

## Lister des fichiers/dossiers

`ls` - Affiche les dossiers

`ls -l` - Afficher les dossier/fichier, avec le droit , la taille , propriétaire et groupe, (utiliser un format d'affichage long)

`ls -lh` Afficher les dossier/fichier, avec le droit , la taille , propriétaire et groupe (afficher les tailles en format lisible (par exemple 1K, 234M ou 2G))

`ls -al` Affiche la liste de tous les fichiers avec tous les fichiers cachés dans le système de répertoire actuel de Linux

Pour plus d'info sur la commande **[ls](http://manpages.ubuntu.com/manpages/focal/fr/man1/ls.1.html)**.

## Création et visualisation de fichiers

Crée un nouveau fichier avec la commande suivante

    I. cat > votrefichier.txt
    II. Ajouter du contenue
    III. Appuyer sur `ctrl + c`pour sauvegarder puis revenir sur la console

En plus simple
    `echo "Votre text" > ./votrefichier.txt`
Vous pouvez aussi choisir l'emplacement du fichier.
      `echo "Bienvenue sur mon site" > /var/www/index.html`

Pour visualiser le contenue d'un fichier.
    `cat ./votrefichier.txt`

## Chercher un fichier

`find / −name index.js −print` - Va me lister tout les fichier portant comme nom **index.js**.
`find /var/www/ -name "*.html" -print` Me liste tout les fichier portant comme extention **.html**.
`find /var/www/monsite -name "*.html" −print −exec rm {} \;` Me liste tout les fichier portant comme extention **.html**, puis les supprimes.

Décomposition de cette commande `find /var/www/ -name *.html -print`

        find - chercher.
        /var/www/ - le dossier dans lequelle je veut que il face une recherche.
        -name - est l'option qui indique ici que nous voulons spécifier le nom d'un fichier.
        −print - affiche le résultat.

<!--
Décomposition de cette commande `find /var/www/ -name index.php -print -ok 'rm' {} \;`

        **find** => chercher,
        **/var/www/** => le dossier dans lequelle je veut que il face une recherche,
        **-name** => est l'option qui indique ici que nous voulons spécifier le nom d'un fichier.
        **−print** affiche le résultat.
        **-ok** Demande une confirmation avant suppréssion, si vous remplacer le `-ok` par `-exec` aucune confirmation ne serra demander.
        **rm** => Supprime le fichier
        **{}**
-->

## Trouver du texte dans un fichier

`grep [mot] [fichier]`

Exemple dans le cas dans fichier *html*

`grep samuel index.html` - Il ma m'indiquer tout les **Samuel** dans le fichier **index.html**.

Si vous souhaitez ajouter le numéros des lignes il faut ajouter l'option **-n**.

`grep -n samuel index.html` - Il ma m'indiquer tout les **Samuel** dans le fichier **index.html** avec le numéro de ligne.
