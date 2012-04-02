.. _creating_db:

Partie 3 : Créer une base de données spatiales
===============================================

PgAdmin
-------

.. note::

  La base de données PostGIS a été installée sans la moindre restriction d'accès pour les utilisateurs locaux (les utilisateurs se connectant sur la même machine que celle faisant tourner le serveur de base de données). Cela signifie qu'il acceptera *tous* les mots de passe que vous fournirez.


PostgreSQL et PostGIS sont déjà installés et sont lancés en tâche de fond. Nous pouvons donc lancer PgAdmin pour se connecter. Il s'agit du client avec interface graphique de PostgreSQL.

.. note:: 

         PostgreSQL dispose de nombreux outils d'administration différents.  Le premier est `psql <http://www.postgresql.org/docs/8.1/static/app-psql.html>`_ un outil en ligne de commande permettant de saisir des requêtes SQL. Un autre outil d'administation populaire est l'outils graphique libre et gratuit `PgAdmin <http://www.pgadmin.org/>`_. Toutes les requêtes exécutées depuis PgAdmin peuvent aussi être utilisées depuis la ligne de commande avec psql. 

#. Si c'est la première fois que vous lancez PgAdmin, vous devriez avoir une entrée du type **PostGIS (localhost:5432)** déjà configurée dans pgAdmin. Double cliquez sur cet élément, et entrez le mot de passe de votre choix pour vous connecter au serveur.

    .. image:: ./screenshots/pgadmin_01.png

    .. note::

      Si vous n'avez pas déjà une entrée **(localhost:5432)**. Vous devrez créer une nouvelle connexion. Allez dans *File > Add Server*, puis enregistrez un nouveau serveur pour **localhost** avec le port **5432** afin de vous connecter au serveur PostGIS installé.

Créer une base de données
-------------------------

PostgreSQL fournit ce que l'on appèle des modèles de bases de données qui peuvent être utilisés lors de la création d'une nouvelle base. Cette nouvelle base contiendra alors une copie de tout ce qui est présent dans le modèle. Lorsque vous installez PostGIS, une base de données appelée ``template_postgis`` a été crée. Si nous utilisons ``template_postgis`` comme modèle lors de la création de notre nouvelle base, la nouvelle base sera une base de données spatiales.

#. Ouvrez l'arbre des bases de données et regardez quelles sont les bases de données disponibles. La base ``postgres`` est la base de l'utilisateur (par défaut l'utilisateur postgres, donc pas très interressante pour nous). La base ``template_postgis`` est celle que nous utiliserons pour créer des bases de données spatiales.

#. Cliquez avec le clic droit sur l'élément ``Databases`` et selectionnez ``New Database``.

   .. image:: ./screenshots/pgadmin_02.png

   .. note:: Si vous recevez un message d'erreur indiquant que la base de données (``template_postgis``) est utilisée par d'autre utilisateurs, cela signifie que vous l'avez activé par inadvertance. Utilisez alors le clic droit sur l'élément ``PostGIS (localhost:5432)`` puis sélectionnez ``Disconnect``.  Double cliquez sur le même élément pour vous reconnecter et essayez à nouveau.

#. Remplissez le formulaire ``New Database`` puis cliquez sur **OK**.  

   .. list-table::

      * - **Name**
        - ``nyc``
      * - **Owner**
        - ``postgres``
      * - **Encoding**
        - ``UTF8``
      * - **Template**
        - ``template_postgis``

   .. image:: ./screenshots/pgadmin_03.png

#. Selectionnez la nouvelle base de données ``nyc`` et ouvrez-la pour consulter son contenu. Vous verrez le schéma ``public``, et sous cela un ensemble de tables de métadonnées spécifiques à PostGIS -- ``geometry_columns`` et ``spatial_ref_sys``.

   .. image:: ./screenshots/pgadmin_04.png

#. Cliquez sur le bouton SQL query comme présenté ci-dessous (ou allez dans *Tools > Query Tool*).

   .. image:: ./screenshots/pgadmin_05.png

#. Saisissez la requête suivante dans le champ prévu à cet effet :

   .. code-block:: sql

      SELECT postgis_full_version();

   .. note::
   
      C'est notre première requête SQL.  ``postgis_full_version()`` est une fonction d'administration qui renvoit le numéro de version et les options de configuration utilisées lors de la compilation. 
      
#. Cliquez sur le bouton **Play** dans la barre d'outils (ou utilisez la touche **F5**) pour  "exécuter la requête." La requête retournera la chaîne de caractères suivante, confirmant que PostGIS est correctement activé dans la base de données.

   .. image:: ./screenshots/pgadmin_06.png
   
Vous venez de créer une base de données PostGIS avec succès !

Liste des fonctions
-------------------

`PostGIS_Full_Version <http://postgis.org/documentation/manual-svn/PostGIS_Full_Version.html>`_: Retourne les informations complètes relatives à la version et aux options de compilation de postgis.
