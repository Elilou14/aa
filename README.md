
# MT4 Production Project
## The objective of this project is a Master Tech Lead level challenge whose stages are:
You must be able to log in as an admin, add a promo, and provide the precise link to the students of each promo. By clicking on this link, the student arrives on the page, creates and validates his account via a magic link (if the first time connected with the e-mail address) and launches the challenge. It is necessary to manage the case where the students already have an account. Students fill in the necessary contact details and launch the challenge. The challenge must be able to connect to its instance, perform tasks and validations, and return errors if necessary. Errors expose what is requested, or it is the error message transferred from the test instance so that students can properly read and correct the problem. Each time the challenge is relaunched, the score is reset to zero. There may be exceptions where one keeps the score for a particular task permanently. It must be possible to retrieve the scores of the promo in a visual table or to download them.

# Project Title

A brief description of 


## Liens du projet

- Doc App -> https://mt4challenge.onrender.com/swagger/app
- Doc Back-office -> https://mt4challenge.onrender.com/swagger/app
- Prod App -> https://mt4challenge.netlify.app/
- Prod Back-office -> https://mt4challenge-back-office.netlify.app/


## Questions/answers

- 1er défi -> créer un fichier helloworld.txt et mettre dedans Hello, World!
- 2eme défi -> créer un fichier byebyeworld.txt et mettre dedans Bye, Bye, World!
- 3eme défi -> télécharger un fichier et mettre le contenu dans un dossier appelé "bastien"
- 4e et dernier -> créer un script today_french.sh qui doit retourner la 18 avril 2024
Texte du projet : 

1 -> Bienvenue au premier défi !<br/>Pour ce premier défi, nous allons commencer par une 
tâche fondamentale: créer un fichier <code>helloworld.txt</code>, le fichier doit contenir le texte "Hello, World!". Cela peut sembler simple, mais c'est en fait un élément clé de la programmation, car c'est souvent le premier programme qu'un développeur écrit en apprenant un nouveau langage de programmation'

2 -> Vous devez créer un fichier <code>byebyeworld.txt</code>, le fichier doit contenir le texte "Bye Bye, World!".

3 -> Pour ce challenge, il est nécessaire de télécharger ces fichier (https://we.tl/t-jYOz9v07GF).<br/>Nous avons besoin de compter le nombres de fichier contenant l'extension <code>js</code>, <code>json</code> ou <code>py</code>. Attention! Nous voulons ignorer les fichiers dont la taille est inférieure à 500 kilobytes (kB). Veuillez créer un script <code>count_files.sh</code>

4 -> Créer le script <code>today_french.sh</code> qui retourne la date en français dans le format suivant <code>18 avril 2024</code>


## Answers
## Réponse 1 : 
```shell
1. Ouvre l'interpréteur de commande.
2. Tape "touch helloworld.txt" pour créer un fichier vide nommé helloworld.txt.
3. Tape "echo 'Hello, World!' > helloworld.txt" pour écrire "Hello, World!" dans le fichier.
```
## Réponse 2 : 
```shell
1. Ouvre l'interpréteur de commande.
2. Tape "touch byebyeworld.txt" pour créer un fichier vide nommé byebyeworld.txt.
3. Tape "echo 'Bye, Bye, World!' > byebyeworld.txt" pour écrire "Bye, Bye, World!" dans le fichier.
```
## Réponse 3 : 
```shell
#!/bin/bash

# Variable pour stocker le nombre de fichiers
count=0

# Fonction récursive pour parcourir les fichiers
parcourir_repertoire() {
    local dir="$1"
    for file in "$dir"/*; do
        if [ -f "$file" ]; then
            # Vérifier si le fichier est un fichier texte avec une taille supérieure à 500 ko
            if [[ "$file" == *.json || "$file" == *.js ]] && [ $(du -k "$file" | cut -f1) -gt 500 ]; then
                ((count++))  # Incrémenter le compteur de fichiers
            fi
        elif [ -d "$file" ]; then
            # Appel récursif si le fichier est un répertoire
            parcourir_repertoire "$file"
        fi
    done
}

# Chemin du répertoire "bastien" dans le bureau
directory="./bastien"

# Vérifier si le répertoire existe
if [ ! -d "$directory" ]; then
    echo "Répertoire introuvable."
    exit 1
fi

# Appeler la fonction de parcours du répertoire pour chaque sous-répertoire
parcourir_repertoire "$directory"

# Afficher le nombre de fichiers correspondant aux critères
echo "$count"
}
```

## Réponse 4 : 
```shell
1. Ouvre l'interpréteur de commande.
2. Tape "nano today_french.sh" pour ouvrir l'éditeur de texte nano.
3. Tape les commandes suivantes dans le fichier :

#!/bin/bash
date +"%d %B %Y" | sed 's/January/janvier/;s/February/février/;s/March/mars/;s/April/avril/;s/May/mai/;s/June/juin/;s/July/juillet/;s/August/août/;s/September/septembre/;s/October/octobre/;s/November/novembre/;s/December/décembre/'

4. Sauvegarde le fichier en tapant "Ctrl + O" puis "Enter", puis quitte l'éditeur de texte en tapant "Ctrl + X".
5. Tape "chmod +x today_french.sh" pour rendre le script exécutable.
6. Tape "./today_french.sh" pour exécuter le script et afficher la date en français dans le format demandé.
```
## Color Reference

| Color             | Hex                                                                |
| ----------------- | ------------------------------------------------------------------ |
| Header Background | ![#1B1B38](https://via.placeholder.com/10/1B1B38?text=+) #1B1B38 |
| Font Background | ![#D4D4D4](https://via.placeholder.com/10/D4D4D4?text=+) #D4D4D4 |
| Form Background| ![#32325A](https://via.placeholder.com/10/32325A?text=+) #32325A |


![Logo challenge](logo_challenge_mt4.png)


## Database schema and implementation


![Database schema and implementation](<img src="./db_schema.png" />
)

## Authors
Eliel Hazan, Amanda Elfassy, Djibril Bathily, Illes Taouage, Dorian Vidal


<p align="center">
    <img align="center" src="https://media.giphy.com/media/z5iCvo1oCbqt7ukMQs/giphy.gif">
</p>

