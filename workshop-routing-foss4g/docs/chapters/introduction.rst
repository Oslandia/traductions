==============================================================================================================
Introduction
==============================================================================================================

.. rubric:: Résumé

`pgRouting <http://www.pgrouting.org>`_ ajoute les fonctionnalités de routage à `PostGIS <http://www.postgis.org>`_. Ces travaux pratiques d'introduction vont vous présenter comment. Il présente un exemple pratique de comment utiliser pgRouting avec les données du réseau routier d'`OpenStreetMap <http://www.openstreetmap.org>`_. Il explique les étapes permettant la préparation des données, les requêtes de routage, l'assignation des coûts et l'utilisation de `GeoExt <http://www.geoext.org>`_ pour présenter les chemins depuis une application de web-mapping.

La navigation dans un réseau de routes nécessite des algorithmes de routage complexes qui supportent la restriction des virages utilisables et même des attributs dépendant du temps. pgRouting est une librairie OpenSource qui peut être étendue et qui fournit une grande variété d'outils pour la recherche de plus courts chemins comme une extension de PostgreSQL et de PostGIS. Ces travaux pratiques vont expliquer la recherche de plus courts chemin avec pgRouting dans un réseau routier réel et comment la structure des données est importante pour obtenir des résultats plus rapidement. Vous apprendrez aussi les difficultés et les limitations de pgRouting dans le cadre d'applications SIG.

Pour fournir un exemple concret, ces travaux pratiques utiliseront les données OpenStreetMap de Denver. Vous apprendrez comment convertir les données dans le format requis et comment calibrer les données avec les attributs de "coût". De plus, nuos allons expliquer la différence entre l'algorithme principal de routage "Dijkstra" et "A-Star" ou "Shooting-Star". À la fin de ces travaux pratiques vous aurez acquis une bonne compréhension de comment utiliser pgRouting et comment préparer vos données de réseau.

Pour apprendre comment utiliser la liste des résultats afin de les afficher sur une carte, nous allons contruire une interface graphique de base avec GeoExt. Notre but est de faire ceci de la manières la plus simple possible, et de montrer qu'il n'est pas difficile d'intégrer cela avec les autres outils OpenSource FOSS4G. Pour cette raison, nous avons selectionné GeoExt, qui est une librairie JavaScript fournissant les éléments de base pour créer des applications de webmappping basées sur OpenLayers et Ext.

.. note::

	* Niveau requis : intermédiaire
	* Connaissances requises : SQL (PostgreSQL, PostGIS), Javascript, HTML
	* Matériel : ces travaux pratiques utiliseront le LiveDVD de l'OSGeo.


.. rubric:: Presenter

* *Daniel Kastl* est le fondateur et le directeur de l'entreprise `Georepublic <http://georepublic.de>`_ et travaille en Allemagne et au Japon. Il modère et promeut la communauté pgRouting et en assure le développement depuis 5 ans, il est un actif contributeur de la communauté OSM au Japon.

* *Frédéric Junod* travaille au bureau Suisse de l'entreprise `Camptocamp <http://www.camptocamp.com>`_ depuis environ 5 ans. Il est développeur actif de nombreux projets OpenSource depuis le navigateur (GeoExt, OpenLayers) jusqu'au monde serveur (MapFish, Shapely, TileCache) il est membre du commité de pilotage de pgRouting.

Daniel et Frédéric sont les auteurs des travaux pratiques pgRouting précédents, qui ont eut lieu au FOSS4G au Canada, en Afrique du Sud, en Espagne et dans des conférences locales au Japon.

.. rubric:: License

Ce travail est ditribué sous licence `Creative Commons Attribution-Share Alike 3.0 License <http://creativecommons.org/licenses/by-sa/3.0/>`_.

.. image:: images/license.png


.. rubric:: Support

.. image:: images/camptocamp.png
	:alt: Camptocamp

`Camptocamp <http://www.camptocamp.com>`_

.. image:: images/georepublic.png
	:alt: Georepublic
	
`Georepublic <http://georepublic.de>`_


