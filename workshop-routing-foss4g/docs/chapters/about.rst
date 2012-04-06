=============================================================================================================
À propos
=============================================================================================================

Ces travaux pratiques utilisent de nombreux outils FOSS4G, beaucoup plus que le titre ne le laisse supposer. Ainsi, de nombreux logiciels FOSS4G sont liés aux autres project OpenSource et ce serait aller trop loin de tous les lister. Il y a néanmoins 4 projets OpenSource que ces travaux pratiques présenteront :

.. image:: images/osgeo.png
	:align: center

-------------------------------------------------------------------------------------------------------------
pgRouting
-------------------------------------------------------------------------------------------------------------

pgRouting est une extension de PostGIS et ajoute les fonctionalités de routing au couple PostGIS/PostgreSQL. pgRouting est un développement basé sur pgDijkstra (par `Camptocamp SA <http://www.camptocamp.com>`_). Il a été étendu par l'entreprise `Orkney Inc. <http://www.orkney.co.jp>`_ et est actuellement développé et maintenu par `Georepublic <http://georepublic.de>`_.

.. image:: images/pgrouting.png
	:align: center

pgRouting fournit les fonctions pour :

* Plus court chemin Dikstra : algorithme de routage sans heuristique
* Plus court chemin A-Étoile : routage pour grand un ensemble de données (avec heuristiques)
* Plus court chemin Shooting-Star: routage prenant en compte les sens giratoires (avec heuristiques)
* Problème du voyageur de commerce (TSP)
* Isochrones

De nombreux nouveaux algorithmes vont être ajoutés dans un futur proche :

* Dial-a-Ride-Problem solver (DARP)
* Support du routage multimodal 
* Algorithme de recherche de plus court chemin dépendant du temps / dynamique
* A-Étoile utilisant deux direction 
* All-Pair shortest path algorithm

Les avantages de l'approche base de données pour les algorithmes de routage sont :

* L'accessibilité par de nombreux clients au travers de JDBC, ODBC, ou directement en utilisant Pl/pgSQL. Les clients peuvent être des ordinateurs personnels ou des périphériques mobiles.
* Utilise PostGIS pour le format des données géographiques, qui utilise le Format Text Bien Connu (WKT) de l'OGC et le Format Binaire Bien Connu (WKB).
* Les logiciels OpenSource comme QGIS et uDig peuvent modifier les données / les attributs.
* Les modifications apportées aux données peuvent être intégrées au moteur de routage instantanément. Il n'y pas de besoin de pré-calcul.
* Le paramètre de "coût" peut être calculé dynamiquement à l'aide du SQL et ces valeurs peuvent provenir de différets attributs ou tables.

pgRouting est disponible sous licence GPLv2.

Le site web officiel de pgRouting : http://www.pgrouting.org


-------------------------------------------------------------------------------------------------------------
OpenStreetMap
-------------------------------------------------------------------------------------------------------------

*"OpenStreetMap a pour objectif de créer et fournir des informations géographiques libres telles que des plans de rue à toute personne le désirant. Le projet fut démarré car la plupart des cartes qui semblent libres ont en fait des restrictions d’utilisation légales ou techniques, empêchant de les utiliser de manière créative, productive ou tout simplement selon vos souhaits."* (Source: http://wiki.openstreetmap.org/wiki/FR:Portal:Press)

.. image:: images/osm_logo.png
	:align: center

OpenStreetMap est une source de données intéressant pour être utilisée avec pgRouting, car celles-ci sont librement disponibles et n'ont pas de restrictions techniques en terme d'utilisation. L'exhaustivité des données varie d'un pays à un autre, mais la couverture mondiale s'améliore de jour en jour.

OpenStreetMap utilise une structuration de données topologique :

* Les noeuds (nodes) sont des points avec une position géographique.
* Les chemins (ways) sont des liste de noeuds, représentant une polyligne ou un polygone.
* Les relations (relations) sont des groupes de noeud, de chemin et d'autres relations auxquelles on peut affecter certaines propriétés.
* Les propriétés (tags) peuvent être appliquées à des noeuds, des chemins ou des relations et consistent en un couple nom=valeur.

Site web d'OpenStreetMap : http://www.openstreetmap.org


-------------------------------------------------------------------------------------------------------------
osm2pgrouting
-------------------------------------------------------------------------------------------------------------

osm2pgrouting est un outil en ligne de commande qui rend simple l'importation de données OpenStreetMap dans une base de données pgRouting. Il contruit le réseau routier automatiquement et crée les tables pour les types de données et les classes de routes. osm2pgrouting a été écrit initialement par Daniel Wendt et est maintenant disponible sur le site du projet pgRouting.

osm2pgrouting est disponible sous licence GPLv2.

Site web du projet : http://www.pgrouting.org/docs/tools/osm2pgrouting.html


-------------------------------------------------------------------------------------------------------------
GeoExt
-------------------------------------------------------------------------------------------------------------

GeoExt est une librairie JavaScript destinée aux applications web avancées. GeoExt rassemble les connaissances géospatiales de `OpenLayers <http://www.openlayers.org>`_ avec une interface utilisateurs issue de `Ext JS <http://www.sencha.com>`_ pour aider à construire des applications web ressemblant à des applications bureautiques.

.. image:: images/GeoExt.png
	:align: center

GeoExt est disponible sous licence BSD et est maintenu par une communauté grandissante d'individus, d'organisations et d'entreprises.

Le site web de GeoExt : http://www.geoext.org
