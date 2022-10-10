## Gestion des utilisateurs et des groupes


1. Création de 2 groupes : sudo groupadd dev
	sudo groupadd infra
2. Création de 4 utilisateurs avec leur dossier personnel : sudo -m useradd alice
	sudo useradd -m bob
	sudo useradd -m charlie
	sudo useradd -m dave
   Modification du shell en bash :
	sudo usermod -s /bin/bash alice
	sudo usermod -s /bin/bash bob
	sudo usermod -s /bin/bash charlie
	sudo usermod -s /bin/bash dave
3.  Ajout dans un groupe créé : usermod -a -G dev alice
	usermod -a -G dev bob
	usermod -a -G dev dave	
	usermod -a -G infra bob
	usermod -a -G infra charlie
	usermod -a -G dev dave
4.  Afficher les membres d'infra : cat /etc/group
	sudo cat /etc/gshadow
5.  Faire de dev le groupe propriétaire des répertoires : sudo chgrp dev alice
	sudo chgrp dev bob
	sudo chgrp infra dave
	sudo chgrp dev charlie
6.  Remplacer groupe primaire : sudo usermod alice -g dev
	sudo usermod bob -g dev
	sudo usermod alice -g infra
	sudo usermod dave -g infra
7.  sudo mkdir dev et sudo mkdir infra: création des dossiers infra dans home
	sudo chgrp dev dev : attribution du groupe dev au dossier 
	sudo chgrp infra infra : attribution du groupe infra au dossier 
	sudo chmod g+w dev : attribution des permissions pour lecture 
	sudo chmod g+w infra : attribution des permissions pour lecture
8.  Seul le propriétaire d’un fichier ait le droit de renommer ou supprimer le dossier dev : sudo chmod +t dev
9.  Il est impossible d'ouvrir une session en tant que Alice. Le mot de passe n'étant pas encore paramétré, le compte n'est pas activé.
10. Activation du compte utilisateur : sudo passwd alice
11. id alice : trouve le uid et gid
12. utilisateur uid 1003 : id 1003
