# LAB1-IAC-VAGRANT

Ce travail représente mon premier Lab sur l'infrastructure as code avec Vagrant et Ansible. Ici, vous trouverez tous les éléments nécessaires a
la création des machines virtuelles avec Vagrant tels que les vagrantfile.

## Overview
Ci dessous, un aprecu du lancement d'un playbook ansible sur 2 noeuds cibles.

https://github.com/Anida-Assane/LAB1-IAC-VAGRANT/assets/96641266/bc4beb8b-2f9a-45ca-b298-2641e7a5fa8c

### Approvisionnement des VM avec Vagrant
Pour creer nos machines virtuelles, nous allons creer pour chacune d'entre elles un dossier, puis dans ce dossier, nous initialiserons le vagrantfile a l'aide de la commande ci dessous, avec comme nom de notre 
image "centos/7
```
vagrant init centos/7
```

