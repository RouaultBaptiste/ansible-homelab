# Ansible SOC Automation

Automatisation de la sécurité, du hardening et de la réponse aux incidents
pour une infrastructure Linux (PME / SOC).

## Fonctionnalités
- Hardening OS & SSH
- Déploiement Wazuh Agent
- Réponse automatique aux incidents
- Isolation réseau contrôlée
- Architecture SOC-ready

## Cas d’usage
- Onboarding automatique de nouvelles machines
- Réponse à une brute force SSH
- Contention d’incident

## Lancement rapide
```bash
ansible-playbook playbooks/cyber_baseline.yml
