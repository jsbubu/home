### Auteurs : Jean-Sébastien BUGAND-BUGANDET et Loris MERCIER
# TPP 1 - Installation d’Ubuntu Server et prise en main du shell

# Exercice 2. Prise en main de l’interpréteur de commandes
## Manuel
**1.** Grâce à la commande **_man which_** on peut observer que cette commande permet de connaître le chemin d'exécution des différents alias. 
**Par exemple :** _Which ls_ nous donne : /usr/bin/ls

**2.** En ajoutant **_| grep option_** à la commande **_man which_** nous pouvons trouver rapidement toutes les lignes ou se trouve l’attribut “option”.

**3.** Pour quitter le manuel il suffit d’appuyer sur “q”.

**4.** Pour accéder à la 6éme section du man, nous utilisons la commande  **_man “numéro de section” “nom de la commande_**

## Navigation dans l’arborescence des fichiers
**1.** Pour accéder au dossier log : **_cd /var/log_**
**2.** Pour accéder au dossier parent : **_cd .. _**
**3.** Pour accéder au dossier personnel : **_cd ~ _**
**4.** Pour accéder au dossier de la dernière recherche : **_cd - _**
**5.** cd /root → permission denied
**6.** sudo cd /root → commande non trouvé
**7.** 
* cd
* mkdir Dossier1 Dossier2
* cd Dossier1
* touch Fichier1
* cd
* cd Dossier2
* mkdir Dossier2.1 Dossier2.2
* cd Dossier 2.2
* Touch Fichier2 Fichier3
**8.** rm Fichier1 → suppr fichier
**9.** rmdir Dossier1 → suppr dossier
**10.** erreur avec rmdir Dossier2
**11.** normal faut faire en récursif → rmdir -r

## Commandes importantes
**1.** time → détermine temps d'exécution d’une tâche
**ex : time ls**
C’est date pour avoir l’heure ;)
**2.** ls --> affiche dossier
**la**  → affiche tous les dossiers visibles et cachés
**3.** which ls → /usr/bin/ls
**4.** ll → affiche tous les dossiers + détails
ll = ls -alF (all, long et classify)
**5.** ls /bin
**6.** ls .. → affiche le contenu du dossier situé avant
**7.**pwd → chemin du dossier courant
**8.** echo ‘yo’ > plop → créer un fichier plop avec “yo”
**9.** echo ‘yo’ >> plop → ajoute “yo” à un fichier plop
**10.** file → détermine le type du fichier
**11.** echo ‘Hello World !’ > toto
raccourci titi vers fichier toto --> ln toto titi
titi fonctionne même si toto est modifié, et il affiche le dernier contenue de toto quand il est supprimé.
12. On peut faire un ln titi tutu mais pas inverse, on suppr le titi et tutu affiche le dernier contenu de titi
13. more /var/log/syslog
et appuyer sur espace pour continuer d’afficher
14. head -n 5 /var/log/syslog → affiche les 5 premières lignes
tail -n 15 /var/log/syslog → affiche les 15 dernières lignes
head -n 20 /var/log/syslog | tail -n 10
15. dmesg est une commande sur les systèmes d'exploitation de type Unix qui affiche la mémoire tampon de message du noyau
less est une commande Unix permettant de visualiser un fichier texte page par page (sans le modifier). Sa fonction est similaire à la commande more, mais permet en plus de revenir en arrière ou de rechercher une chaîne.
dmesg  | less → affiche mem tampon, on peut aller en avant et en arriere page par page.
16. /etc/passwd → fichier mdp user
man passwd
17. afficher 1ere colonne par ordre alphabétique inverse → sort -k1dr
18.cat /etc/passwd | awk -F: '{print $ 1}' → affiche les users
19. apropos est une commande Unix qui permet de lister les manuels dont la description comprend les mots passés en arguments.
apropos conversion 
20. find -name passwd → à la racine pour trouver touts les fichiers nommés passwd
21.find -name passwd > ~/list_passwd_files.txt 2> /dev/null
22.sort /home/js/.bashrc | grep ll → cherche ou est def alias ll
23.locate .history → localise fichier history.log
24. pour les fichiers récents il faut faire updatedb, puis on fait le locate.




# Exercice 3. Découverte de l’éditeur de texte nano

F1 ou Ctrl + G Affichage de l’aide 
Ctrl + X Quitter nano / Fermer une fenêtre / Exécuter une commande Ctrl + R Ouvrir un fichier 
Ctrl + O Enregistrer sous 
Ctrl + S Enregistrer 
Ctrl + K Couper 
Ctrl + U Coller 
Ctrl + W Rechercher 
Ctrl + \ Remplacer 
Ctrl + C Afficher des informations sur la position du curseur (numéro de ligne, de colonne) 
Alt + U Annuler 
Alt + E Refaire 

# Exercice 4. Personnalisation du shell

**1.** Pour créer une copie du bash il suffit de faire **_cp .bashrc .bashrc_bak_**

**2.** Pour décommenter la ligne force_color_prompt=yes il faut : 
* nano .bashrc
* enlever le # de force_color_prompt=yes
* CTRL + x pour quitter 
* Y pour sauvegarder
* Entrer pour valider 

**3.** Le fichier .bashrc est lu au démarrage du shell ; pour le recharger, il faudrait donc se déconnecter puis se reconnecter ; mais il existe un autre moyen : la commande  **_source .bashrc _**. L’invite de commande devrait immédiatement passer en couleurs.

**4.** Modifiez l’invite de commande pour qu’elle s’affiche sous la forme suivante :
* nano .bashrc
* remplacer la ligne par :
PS1='${debian_chroot:+($debian_chroot)}\033[91m\][\A] \033[00m\]- \[\033[01;32m\]\u@\h\[\033[00m\]:\[\033[01;36m\]\w\[\033[00m\]\$ '

# Exercice 5. Pour les plus rapides


