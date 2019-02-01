Architecture
============

Une des principales différences entre MASH et les autres modèles systémiques ou conceptuels réside dans son architecture particulière associant fonction de transfert en série et en parallèle, ainsi que dans sa versatilité lui permettant de s’adapter à un grand nombre de situation, étant donné que le modèle peut utiliser d’une à douze fonctions de transfert (quatre branches en parallèle de chacune trois fonctions en série).

Le nombre d’entrées, compris entre un et quatre, définit également le nombre de branches parallèles que comporte le modèle. Le nombre de fonctions de transfert en série, compris entre un et trois, impose la taille de chacune des branches. Le type de fonction de transfert paramétrique est choisi pour chacune des fonctions du modèle au sein d’une bibliothèque comportant actuellement quatre fonctions type mais pouvant être étendue ultérieurement.

MASH possède donc dans sa version la plus simple une entrée et une fonction de transfert, et dans sa version la plus complexe quatre entrées et douze fonctions de transfert.




La sortie :math:`S (t )` est calculée comme étant la somme des produits de convolutions des entrées par les fonctions de transfert de chaque branche :

:math:`S ( t ) = E _ { 1 } * H _ { 1 } ^ { e q } ( t ) + E _ { 2 } * H _ { 2 } ^ { e q } ( t ) + E _ { 3 } ^ { * } H _ { 2 } ^ { e q } ( t ) + E _ { 4 } ^ { * } H _ { 2 } ^ { e q } ( t )`

où :math:`E_i` est la ième entrée du modèle et :math:`H _ { i } ^ { e q }` est la ième fonction de transfert équivalente égale au produit de convolution des trois fonctions de transfert élémentaires d’une branche :

:math:`H _ { i } ^ { e q } ( t ) = K _ { i } ^ { e q } \cdot \left( H _ { i } ^ { 1 } * H _ { i } ^ { 2 * } H _ { i } ^ { 3 } ( t ) \right)`

où :math:`K _ { i } ^ { e q }` est le gain de la ième branche et :math:`H _ { i } ^ { \alpha }` est la α\ :sup:`ème` fonction de transfert de la ième branche. Les fonctions de transfert élémentaires inutilisées sont égales à la distribution de Dirac étant donné que celle-ci est l’élément neutre du produit de convolution.

En couplant cette architecture modulaire avec la possibilité de choisir individuellement chacune des fonctions élémentaires de transfert, les capacités d’adaptation du modèle sont importantes. Dans les modèles à base physique, alors même que les équations explicitant les transferts sont a priori complètement définies en amont au sein du logiciel, l’utilisateur crée un modèle sur mesure adapté au problème (en définissant l’extension du maillage, le nombre de couches géologiques aquifères et aquitards, etc.), Dans une moindre mesure, MASH est également un générateur de modèle à mesure, plus qu’un système figé. En dépit du postulat sur des relations de convolution entre les entrées et la sortie, de nombreuses options sont laissées à l’appréciation du modélisateur afin qu’il dispose d’un modèle adapté au problème qu’il désire résoudre, plutôt que d’essayer de contraindre le problème afin que celui-ci s’adapte au modèle.
