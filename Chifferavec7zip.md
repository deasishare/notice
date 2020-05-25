# Chiffrer ses données avec 7-zip

## Prérequis

- Microsoft Windows
- 7-zip (http://www.7-zip.org/)

## Introduction
Le chiffrement, ou cryptage, consiste à rendre une donnée inexploitable à toute personne ne possédant pas la clé de (dé)chiffrement.

Avec 7-zip, nous allons chiffrer des fichiers et/ou des dossiers
le chiffrement est dit symétrique (la clé de déchiffrement est identique à la clé de chiffrement).

7-zip est avant tout un logiciel de création d'archives, ce qui veut dire qu'il permet de compresser les fichiers avant de les chiffrer. Créer des archives chiffrées avec 7-zip est donc idéal pour échanger des données sensibles ou stocker ces données.

Par contre, créer une archive 7-zip chiffrée implique d'avoir les données en clair sur son disque dur. De même, lors de la lecture du contenu d'une archive, 7-zip va l'extraire dans un dossier temporaire pour permettre aux logiciels concernés d'accéder aux données. Chiffrer ses données grâce à 7-zip ne sécurise donc pas les données sur les ordinateurs qui vont créer ou ouvrir l'archive !

L'intérêt est, par exemple, de protéger les données pendant leur envoi par **email** ou l'echange de données au travers de plate-forme comme **wetransfert**. Si les fichier ou l’émail est intercepté par une personne tierce, celle-ci ne pourra pas lire les données de l'archive sans son mot de passe. C'est également appréciable lorsqu'on sait que la plupart des grands fournisseurs de boites email (pour le grand public) ne suppriment jamais vraiment nos données et y ont accès.

Pour chiffrer des données sur lesquelles on est en train de travailler, il vaut mieux se tourner vers des solutions de chiffrement à la volée, comme TrueCrypt, GPG ou EncFS.

## Chiffrer avec 7-zip

Pour créer une archive chiffrée, il faut procéder de la même manière que pour créer une archive normale avec 7-zip.

La plupart du temps, on sélectionne les fichiers/dossiers qu'on veut placer dans l'archive, on fait un clic droit, et on choisi 7-zip > **Ajouter à l'archive....** On peut également, depuis la fenêtre de 7-zip File Manager, sélectionner les fichiers/dossiers et cliquer sur Ajouter.

Dans les deux cas, la boite de dialogue de création d'archive s'ouvre : "Boite de dialogue de création d'archive"

Voici les principaux réglages pour une archive classique :

- Archive : le nom et l'emplacement où sera créée l'archive
- Format de fichier : je recommande de choisir 7z ; zip est moins performant mais peut servir pour être sûr que l'archive soit lisible par tout le monde
- Niveau de compression : je recommande Ultra pour des données de type textuel, Normal pour des médias dans des formats déjà compressés (jpeg, mp3, ...), ou Aucune si la compression n'est pas nécessaire ou non désirée (très gros fichiers = compression lente)
- Pour chiffrer l'archive, il faut regarder dans la section Cryptage. On a plusieurs réglages :

1. le mot de passe avec lequel on veut chiffrer l'archive (il est masqué à la saisie, donc il faut le saisir deux fois)	
2. Afficher le mot de passe permet de ne pas masquer le mot de passe lors de sa saisie et supprime donc un des deux champs de saisie du mot de passe
3. Méthode de cryptage : je recommande AES-256
4. Crypter les noms de fichier : je recommande de l'activer
5. Il convient de choisir un mot de passe long (> 10 caractères) pour assurer un bon chiffrement. De plus, il est recommander d'échanger ce mot de passe avec le destinataire des données en utilisant un autre moyen de communication.

**Il suffit ensuite de valider et l'archive sera créée !**

## Déchiffrer avec 7-zip
Ouvrir une archive chiffrée se fait de la même manière qu'une archive normale. La plupart du temps, il suffit de double cliquer dessus (depuis l'explorateur de fichiers ou depuis 7-zip File Manager).

Si Crypter les noms de fichier a été coché à la création de l'archive, le mot de passe est demandé.

Lorsque le mot de passe a été saisi, il est possible d'accéder au contenu de l'archive.

Si Crypter les noms de fichier n'a pas été coché à la création de l'archive, l'archive s'ouvrira normalement et on pourra voir la liste des fichiers/dossiers qu'elle contient. Le mot de passe sera demandé dès qu'on accédera à un des fichiers.
