Fonctions de transfert
======================

On rappelle que MASH permet de choisir chacune des fonctions de transfert dans une bibliothèque de fonctions. Cette bibliothèque est pour l’instant assez réduite car elle ne comporte que quatre fonctions de transfert mais étant donnée l’architecture du modèle, ajouter de nouvelles fonctions ne pose aucun problème majeur du point de vue du développement logiciel. Après avoir réalisé qu’il n’existait pas dans la littérature de relation bijective entre la FTP utilisée et l'hydrosystème représenté (i.e. une même fonction de transfert peut modéliser plusieurs phénomènes, et la réponse d'hydrosystèmes de même nature peut être approchée par plusieurs fonctions), le choix a été fait de sélectionner des fonctions de transfert utilisables selon trois critères : leur faible paramétrisation, leur caractère général et leur interprétation physique.

La faible paramétrisation permet au modèle global d’être parcimonieux et d’éviter « la malédiction de la dimension » lors de la procédure d’optimisation. Les fonctions restent simples et la complexité provient uniquement de la mise en série/parallèle de fonctions élémentaires. Le sens physique de cette mise en série (évènements successifs dans le temps ou l'espace) ou parallèle (évènements concomitants ou disjoints spatialement) est simple et relativement facile à jauger au regard de la réalité du problème modélisé. Le caractère général représente la capacité d’une fonction de transfert à englober d’autres modèles plus simples selon la valeur de ses paramètres. Une même fonction représente ainsi plusieurs modèles, ce qui facilite la programmation du logiciel et augmente les possibilités offertes. L’interprétation physique apporte les avantages des modèles conceptuels à la modélisation systémique comme l’interprétation phénoménologique du fonctionnement du système et l’éventuel rapprochement entre les paramètres du modèle et les caractéristiques physiques du terrain.

Les quatre fonctions de la bibliothèque de MASH sont toutes des fonctions de densité de probabilité : loi Gamma, loi normale, loi Bêta et loi de puissance (les fonctions ci-dessous ne sont pas toutes normalisées par un coefficient multiplicateur qui amènerait leur intégrale à un. On verra plus loin que ce coefficient peut être assimilé dans le gain de la branche du modèle).


Loi Gamma
---------

:math:`H ( t ) = \frac { 1 } { k \Gamma ( n ) } \left( \frac { t } { k } \right) ^ { n - 1 } \mathrm { e } ^ { - t / k }`

avec :math:`\Gamma ( \mathrm { n } ) = \int _ { 0 } ^ { \infty } t ^ { n - 1 } e ^ { - t } \mathrm { d } t`


Loi Gamma
---------

:math:`H ( t ) = \mathrm { e } ^ { - \frac { ( t - T ) ^ { 2 } } { \sigma ^ { 2 } } }`


Loi Bêta
--------

:math:`H ( t ) = \frac { t ^ { n - 1 } ( 1 - t ) ^ { m - 1 } } { \beta ( n , m ) }`
:math:`\beta ( x , y ) = \int _ { 0 } ^ { 1 } t ^ { x - 1 } ( 1 - t ) ^ { y - 1 } d t`


Loi de puissance
----------------

:math:`H ( t ) = \frac { 1 } { ( 1 + \alpha t ) ^ { n } }`
