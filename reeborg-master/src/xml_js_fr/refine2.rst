`Précédent <Javascript:void(0);>`__ `Table des
matières <Javascript:void(0);>`__ `Suivant <Javascript:void(0);>`__

Améliorations: partie 2
=======================

Je suis certain que vous avez trouvé la source du problème de la
solution présentée lors de la dernière leçon: Reeborg déposait un jeton
et, avant même de se déplacer, il vérifiait s'il était arrivé à son but
en cherchant pour un jeton qui, évidemment, se trouvait là où il était.
Donc, la boucle ``while`` n'était jamais exécutée. Voici un programme
modifié qui devrait fonctionner:

.. code:: jscode

    dépose("jeton");
    avance();
    while ( !jeton_ici() ){
        if (rien_devant()){
            avance();
        } else {
            tourne_à_gauche();
        }
    }

**Vérifiez-le!**

Un monde un peu plus complexe
-----------------------------

Essayons de modifier le programme pour qu'il puisse également être une
solution pour le monde Autour 2. Sélectionnez donc ce monde et exécuter
le programme que vous avez déjà sans le modifier pour voir ce qui
arrive.

Identifier le problème
----------------------

Comme vous avez pu le constater en exécutant le programme ci-dessus, le
résultat n'était pas celui désiré: Reeborg prend un raccourci et ne fait
pas le tour du monde. Le problème est que nous avions supposé que
Reeborg n'ait que deux options: avancer ou tourner à gauche. Nous
n'avons pas tenu compte de situations où Reeborg devrait tourner à
droite. Donc, ce que Reeborg devrait faire est en premier de vérifier
s'il y a un mur à sa droite; si la réponse est non, alors il doit faire
un virage à droite pour suivre le mur. Voici un programme modifié qui
est une tentative de résoudre le problème.

.. code:: jscode

    dépose("jeton");
    avance();
    while ( !jeton_ici() ){
        if (right_is_clear()){
            tourne_à_droite();
        } else if (rien_devant()){
            avance();
        } else {
            tourne_à_gauche();
        }
    }

Est-ce que ceci fonctionne? Lisez et analysez soigneusement ce programme
puis confirmer votre opinion en l'exécutant. Si vous pouvez pensez à des
améliorations à apporter au programme, faites-les avant de passer à la
leçon suivante.

`Précédent <Javascript:void(0);>`__ `Suivant <Javascript:void(0);>`__
