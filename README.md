# ansible

Ce dépôt contient des scripts et des rôles Ansible pour automatiser la gestion et la configuration de vos serveurs.

## Prérequis

- [Ansible](https://www.ansible.com/) installé sur votre machine
- Accès SSH aux serveurs à configurer

## Commandes ad-hoc

Créer un fichier d'inventaire en .ini ou .yml :

hosts.yml
```bash
---
all: 
  vars:
    ansible_ssh_common_args: "-o StrictHostKeyChecking=no"
prod:
  hosts:
    client: 
      ansible_host: 10.0.36.5
      ansible_connection: local

```

Utiliser un module ping :

```bash
ansible -i inventaire all -m ping
```

Utiliser un module copy (copier un fichier sur machine distance) :

```bash
ansible -i inventaire all -m copy -a "dest=/home/admin/toto.txt content='Hello World'"
```

Utiliser un module setup :

```bash
ansible -i inventaire all -m setup
```


## Installation

Clonez ce dépôt :

```bash
git clone https://github.com/votre-utilisateur/ansible.git
cd ansible
```

## Utilisation

Validation syntaxique d'un playbook :

```bash
ansible-playbook  -i inventaire playbook.yml 
```

Exécutez un playbook :

```bash
ansible-playbook  -i inventaire playbook.yml 
```

## Structure du projet

- `playbook.yml` : Exemple de playbook principal
- `roles/` : Dossier contenant les rôles Ansible
- `inventaire` : Fichier d'inventaire des hôtes

## Contribution

Les contributions sont les bienvenues ! N'hésitez pas à ouvrir une issue ou une pull request.

## Licence

Ce projet est sous licence MIT.