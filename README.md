

### Historique des modifs:

## 9 mars: Olivier 1

-insertion d'une constante pour la taille des lignes
-modification du de la fonction de lecture avec quelques lignes modifiées, mais pas d'une très grande importance
-ajout de la fonction affichageChaine qui n'est pas obligatoire mais qui permet de vérifier des infos
-implémentation de la fonction d'affichage graphique(j'ai aussi mis une constante pour modifier la taille du graphe)
-modif du makefile en conséquences
-fonctions de distance et de dénombrement des points


## 20 mars: Olivier

-Modification de beacoup de fichier
-Ajout de la fonction de recherche des voisins d'un noeud pour la question 2.2
-Ajout de ma fonction ReconstitueReseauListe mais sans la tester
-Ajout d'un fichier test du Resau mais que je n'ai pas encore eu le temps de tester. Pour le moment, sa règle 
compile

## 26 mars: Olivier

-Grosse modification de la fonction de reconstitution du réseau, qui est désormais viable. En effet, je n'utilisais pas la fonction de l'exo de recherche/ajout pour l'ajout des voisins d'un Noeud. Par conséquent le programme créait un Noeud à chaque recherche de voisin, même s'il existait déjà dans le Réseau. Du coup, il n'y avait aucun noeud qui se répétait dans l'ensemble des voisins à l'affichage, ce que je trouvais étrange. En fait, il faut bien comprendre que les noeuds du réseau sont les noeuds réels, mais que les voisins symbolisent les ports. Donc il doit y avoir des répétitions dans les voisins des noeuds, s'il y a plusieurs câbles qui relient le même.


## 30 mars: Olivier 

Exo 4 terminé. Le concept est globalement le même que celui de l'exo d'avant, mais il faut désormais créer un reseau avec une table de hachage. Il faut veiller à initialiser tous ses champs à NULL, lors de la création, et tout va bien se passer. Par contre, bizarrement, le code me génère une erreur à l'exécution sur mac, alors qu'il fonctionne sur linux.

## 9 avril: Olivier

Exo sur les arbres terminé, mais pas très satisfait, car le programme ne pourrait pas fonctionner si l'écart minimal entre deux points du réseau était inférieur à 0.2. Actuellement, le code fonctionne, mais on n'est vraiment pas loin d'une erreur de surcharge de la pile d'exécution. En bref, dans le cas d'un réseau réel, ça ne fonctionnerait pas du tout.

Update de la même journée: Je me suis rendu compte avec un papier que c'était totalement impossible que deux points aussi proches qu'ils soient ne pouvaient en aucun cas se retrouver à une telle distance que la pile soit obligée d'être surchargée avant qu'ils soient atteints. 

Il y avait plusieurs erreurs:
1: Lorsqu'un arbre était vide dans la fonction d'insertion (le premier cas), il était tout le temps inséré au sud est (ou au nord ouest je sais plus)

2: Comme la racine était diférente du pointeur vers l'arbre, dans les fonctions, l'adresse de l'arbre (*a) était toujours celle du premier arbre, avec pour parent la racine. C'est pour cela que des certains points n'étaient jamais trouvés.

3: J'ai en bonus modifié les coordonnées des points en leur enlevant le minimum, pour que ce soit plus simple de comprendre. Le minimum vaut donc zero, et tous les autres points ont des valeurs "normales". Mais du coup, j'ai été obligé de faire quelques concessions sur a tête du code à certains endroits. Il y a des paramètres en plus pour enlever les valeurs xmin et ymin. Enfin, une fonction pour remettre les valeurs de départ. Bref c'est moche mais ça marche de façon fiable. Mais du coup, ça peut être amélioré. 

## 14 avril: Olivier

J'ai été obligé de modifier la structure générale du code en ajoutant un paramètre pour la table de hachage, afin de pouvoir libérer la mémoire. Or ça m'a l'air totalement débile de faire un projet en c si on ne libère rien après. Bref j'ai ajouté des méthodes de libération de mémoires testées et aprouvées pour le réseau en liste et en chaînes de caractères. De plus j'ai créé une nouvelle branche pour le code qui contenait des coordonnées plus lisibles pour la partie sur l'arbre au cas où j'aurais envie de revenir dessus.

2e commit de la journée: Le code des arbres peut désormais être libéré

## 26 avril : Ludo 

J'ai fini l'exercice 6 mais il y a un problème dans la dernière fonction donc je ne peux pas générer les graphes. J'ai réglé un léger soucis de fuite de mémoire du fichier ChaineMain.c

##  2 mai : Ludo 

J'ai fini l'exercice 7. Je n'ai pas utilisé les fichiers Struct_File car les fichiers file suffisaient. Il reste encore des fuites mémoire à la fin de l'exercice 7. à corriger.
Il faut également ajouter des tests pour les autres fichiers .cha donnés sur Moodle.

### Setup the project

```bash
make
./ReseauMain
```
