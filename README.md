#  Ansible Security Automation Lab

Ce dépôt a pour objectif de présenter un **lab d’automatisation Ansible orienté sécurité**, basé sur des **cas concrets rencontrés en environnement professionnel**.

Il s’agit d’un projet **pédagogique, évolutif et structuré**, permettant de comprendre :
- comment Ansible fonctionne en profondeur
- comment automatiser des configurations systèmes
- comment déployer et sécuriser une infrastructure
- comment intégrer une solution SIEM (Wazuh)
- comment gérer la sécurité côté Active Directory et Linux

---

##  Objectifs du projet

- Automatiser un **lab complet** avec Ansible  
- Appliquer les **bonnes pratiques de sécurité**
- Centraliser les configurations
- Déployer et configurer **Wazuh (manager + agents)**
- Sécuriser des systèmes Linux et Active Directory
- Fournir un projet **lisible, documenté et reproductible**

Ce dépôt est volontairement **très documenté**, afin de servir :
- de support d’apprentissage
- de vitrine GitHub
- de base pour des projets plus avancés

---

##  Ce que permet Ansible dans ce lab

Grâce à Ansible, ce projet permet notamment :

### ⚙️ Automatisation système
- Configuration initiale des serveurs
- Gestion des utilisateurs et des groupes
- Configuration SSH (durcissement, clés, accès)
- Gestion des services système
- Déploiement reproductible

###  Sécurité
- Application de règles de sécurité Linux
- Hardening SSH
- Gestion des permissions
- Centralisation des configurations de sécurité
- Déploiement d’agents de supervision et de sécurité

###  Supervision & SIEM
- Déploiement de **Wazuh Manager**
- Installation automatique des **agents Wazuh**
- Configuration sécurisée des agents
- Centralisation des logs
- Surveillance des événements de sécurité

---

##  Architecture du lab

Le lab est composé de plusieurs briques :

###  Infrastructures
- Serveurs Linux (Debian / Ubuntu)
- Contrôleur de domaine Active Directory
- Serveur Wazuh
- Machines clientes (Linux / Windows)

###  Communication
- Accès SSH sécurisé
- Communication chiffrée entre agents et serveur Wazuh
- Gestion centralisée via Ansible

---

##  Rôles et composants automatisés

Ce projet est structuré autour de **rôles Ansible**, chacun ayant une responsabilité claire.

### Exemples de rôles :
- `common` : configuration de base des serveurs
- `users` : gestion des comptes et groupes
- `ssh` : sécurisation de l’accès SSH
- `security` : règles de durcissement système
- `wazuh_manager` : installation et configuration du manager
- `wazuh_agent` : déploiement des agents
- `ad_integration` : intégration et configuration côté Active Directory

Chaque rôle est :
- isolé
- réutilisable
- documenté

---

## 📁 Organisation du projet

Le dépôt est organisé pour être **lisible et scalable** :

- **inventories/**  
  Gestion des environnements (lab, production, etc.)

- **playbooks/**  
  Playbooks principaux orchestrant les rôles

- **roles/**  
  Rôles Ansible (sécurité, services, supervision)

- **files / templates**  
  Fichiers de configuration complets et templates Jinja2

---

## 🛠️ Fonctionnement global

1. L’inventaire définit les machines cibles
2. Les variables centralisent la configuration
3. Les playbooks orchestrent les rôles
4. Les rôles appliquent :
   - les configurations système
   - les règles de sécurité
   - les services
   - les agents de supervision
5. L’ensemble est **idempotent** :
   - relancer un playbook ne casse rien
   - seules les modifications nécessaires sont appliquées

---

## 🔍 Focus sécurité & Wazuh

### Wazuh est utilisé pour :
- la détection d’intrusion
- la surveillance des logs
- la détection de comportements anormaux
- la conformité sécurité
- la visibilité globale du SI

Les agents sont :
- déployés automatiquement
- configurés de manière cohérente
- reliés au manager de façon sécurisée

---

## 🧪 Environnement de test

- Ansible : >= 2.14
- Python : >= 3.10
- OS Linux : Debian / Ubuntu
- Lab local (VM, Proxmox, VirtualBox, etc.)

---

## 🚀 Lancer le projet

Une fois Ansible installé et l’inventaire configuré :

```bash
ansible-playbook playbooks/site.yml
