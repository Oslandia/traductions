==============================================================================================================
Script PHP coté serveur
==============================================================================================================

Nous utiliserons un script PHP pour exécuter les requêtes de routage et renverrons le résultat au client web.

Les étapes suivantes sont nécessaires :

* Retrouver les coordonnées du point de départ et de celui d'arrivée.
* Trouver l'arête la plus proche d'un point de départ ou d'arrivée.
* Prendre soit le noeud de début ou de fin de l'arête  (pour Dijkstra/ A-Star) ou l'arête elle-même (Shooting-Star) comme début ou fin du parcours.
* Exécuter les requête de recherche de plus court chemin.
* Retourner le résultat de la requête en XML ou mieux encore en GeoJSON au client web.

.. note::
	
	Pour conserver cet exemple aussi simple que possibe et de mettre en évidence les requête de routage, ce script PHP ne valide pas les paramètres des requêtes et ne prend pas en compte les problèmes de sécurité de PHP. 

Commençons avec quelque modèles PHP et plaçons ces fichiers dans un répertoire accessible par le serveur Apache :

.. literalinclude:: ../../web/php/pgrouting.php
	:language: php
	:lines: 1-18

	  
-------------------------------------------------------------------------------------------------------------
L'arête la plus proche
-------------------------------------------------------------------------------------------------------------

Habituellement les points de départ et d'arrivée, qui sont récupérés depuis le client, ne sont pas les points de départ ou d'arrivée d'un tronçon. Il est plus simple de retrouver l'arête la plus proche que le sommet le plus proche, parce que l'algorithme "Shooting-Star" est basé sur les arêtes. Pour les algorithmes basés sur les sommets (Dijkstra, A-Étoile) nous pouvons choisir le point de départ ou d'arrivée de l'arête sélectionnée.

.. literalinclude:: ../../web/php/pgrouting.php
	:language: php
	:lines: 20-56
	  
	  
-------------------------------------------------------------------------------------------------------------
Requête de routage
-------------------------------------------------------------------------------------------------------------

.. literalinclude:: ../../web/php/pgrouting.php
	:language: php
	:lines: 58-116


-------------------------------------------------------------------------------------------------------------
Sortie au format GeoJSON
-------------------------------------------------------------------------------------------------------------

OpenLayers permet l'affichage de lignes en utilisant directement des données au format GeoJSON, donc notre script retourne un objet FeatureCollection au format GeoJSON :

.. literalinclude:: ../../web/php/pgrouting.php
	:language: php
	:lines: 118-

