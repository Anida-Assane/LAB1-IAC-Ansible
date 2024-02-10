# LAB1-IAC-VAGRANT

Ce travail représente mon premier Lab sur l'infrastructure as code avec Vagrant et Ansible. Ici, vous trouverez tous les éléments nécessaires a
la création des machines virtuelles avec Vagrant tels que les vagrantfile. L'hyperviseur de type 2 utilisé dans ce lab est Oracle Vm VirtualBox.

## Overview
Ci dessous, un aprecu du lancement d'un playbook ansible sur 2 noeuds cibles.

https://github.com/Anida-Assane/LAB1-IAC-VAGRANT/assets/96641266/bc4beb8b-2f9a-45ca-b298-2641e7a5fa8c

### Approvisionnement des VM avec Vagrant
Pour creer nos machines virtuelles, nous allons creer pour chacune d'entre elles un dossier, puis dans ce dossier, nous initialiserons le vagrantfile a l'aide de la commande ci dessous, avec comme nom de notre image **centos/7** dans le Vagrant cloud.
```
vagrant init centos/7
```

Une fois le vagrantfile crée, nous allons lancer la Vm a l'aide de la commande suivante

```
vagrant up
```
Lorsque l'on tape cette commande pour la premiere fois, le processus de création de la Vm débutera a l'aide de l'image spécifiée dans le vagrantfile.
Cette image si elle n'est pas stocké localement sur notre machine, un pull sera éffectué depuis le vagrant cloud , puis stockera l'image en local.
Ainsi, l'hyperviseur sera contacté pour créer la machine virtuelle.

Ci dessous, une vidéo explicative de l'architecture de vagrant fais a l'aide du logiciel en ligne draw.io

https://github.com/Anida-Assane/LAB1-IAC-Ansible/assets/96641266/439941cc-d3f8-437a-8ff0-d3c94c887d7a

Une fois les machines crées, l'utilisateur pourras se connecter aux machines a l'aide de SSH grace a la commande

```
vagrant ssh
```

### Gestion de la configuration avec Ansible
Maintenant que nous avons nos machines, nous allons configurer un serveur web apache sur chaque vm.
Dans le tablea ci-dessous, nous avons les informations sur les vm tels que leurs noms et adresses ip, choses importantes pour la création du fichier d'inventaire Ansible.

| Role |  Nom  | @IP |
|:-----|:--------:|------:|
| Noeud de controle   | **vm-control** | 192.168.0.1 |
| Hote géré 1   |  **web1**  | 192.168.0.2 |
| Hote géré 2   | **web2** | 192.168.0.3 |

Pour configurer nos serveurs web apaches, nous procéderont ainsi:
* Installer le paquet httpd
* Activer le service httpd
* copier un fichier web.html sur chaque serveur

> [!NOTE]
> Dans ce lab, nos serveurs sont sur centos 7

Pour la création de nos playbook, nous utiliserons les 3 modules Ansible suivant:
* yum module
* service module
* copy module





