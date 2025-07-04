# Ansible-Galaxy-Eval

Ce dépôt contient un rôle Ansible permettant de déployer automatiquement une instance WordPress avec Apache et MariaDB/MySQL. Ce projet a été réalisé dans le cadre d’une évaluation sur Ansible Galaxy.

## Tester avec le docker compose

Dans l'environnement du LAB Ansible :

1. Rajoutez le dossier deploy_wordpresse et le playbook wp.yml dans le dossier ./projet/playbooks/
2. docker compose up -d
3. ssh root@localhost -p 2222
4. ansible-playbook -i ../inventaire wp.yml

## Structure du projet

- deploy_wordpress : Rôle Ansible principal pour le déploiement de WordPress.
  - `tasks/` : Tâches principales (installation, configuration, sécurisation, etc.).
  - `templates/` : Templates Jinja2 pour la configuration Apache et WordPress.
  - `defaults/` et `vars/` : Variables par défaut et spécifiques.
  - `handlers/` : Handlers pour relancer les services.
  - `files/` : Fichiers statiques à copier.
  - `meta/` : Métadonnées du rôle.
  - `tests/` : Scénarios de test et inventaire.
- wp.yml : Exemple de playbook pour utiliser le rôle.

## Prérequis

- Ansible ≥ 2.9
- Accès root ou sudo sur la machine cible
- Serveur Linux (Debian/Ubuntu recommandé)

## Utilisation

1. Clone le dépôt :
   ```bash
   git clone https://github.com/sseey/Ansible-Galaxy-Eval
   cd Ansible-Galaxy-Eval
   ```

2. Adapte l’inventaire dans inventory selon ta cible.

3. Lance le playbook d’exemple :
   ```bash
   ansible-playbook -i deploy_wordpress/tests/inventory wp.yml
   ```

4. Accède à WordPress via l’URL de ton serveur.

## Personnalisation

- Modifie les variables dans main.yml ou main.yml pour adapter la configuration (nom de la base, utilisateur, mot de passe, etc.).
- Les templates sont personnalisables dans templates.

## Tests

Un scénario de test est disponible dans test.yml.

## Auteur

- Nom : [Ton Nom]
- Contact : [Ton Email]

---

Veux-tu que je l’insère directement dans ton fichier README.md ?