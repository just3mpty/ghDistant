HOOKS - MÉCANISME DE PARTAGE
============================

Ce dépôt contient un répertoire `hooks/` qui regroupe les hooks git utilisés par le projet.
Les hooks git ne sont pas versionnés (répertoire `.git/hooks/` ignoré par git).
Suivre les étapes ci-dessous pour les installer manuellement après avoir cloné le dépôt.

HOOK DISPONIBLE
---------------
hooks/pre-commit
  A chaque commit, demande si le commit doit être vérifié.
  Si 'y' : crée ou met à jour le fichier suivi/commitInfo.txt avec la date et l'heure du commit.
  Si 'n' ou Entrée : le commit se poursuit normalement sans créer le fichier.

INSTALLATION
------------
Option 1 — Copie manuelle (tous OS) :
  Copier le fichier hooks/pre-commit dans le répertoire .git/hooks/ du dépôt local :

    cp hooks/pre-commit .git/hooks/pre-commit

  Puis le rendre exécutable (Linux/Mac/Git Bash) :

    chmod +x .git/hooks/pre-commit

Option 2 — Configuration hooksPath (git >= 2.9) :
  Indiquer à git d'utiliser directement le répertoire hooks/ du projet :

    git config core.hooksPath hooks

  Cette commande est à exécuter une seule fois après le clonage.
  Elle s'applique uniquement au dépôt local (non partagée).

REMARQUES
---------
- Le fichier suivi/commitInfo.txt est versionné et inclus dans le commit.
- Ne pas modifier les hooks directement dans .git/hooks/ ; modifier hooks/pre-commit
  puis réinstaller selon l'option choisie.
