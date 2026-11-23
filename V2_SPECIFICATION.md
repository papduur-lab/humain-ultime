# HUMAIN ULTIME V2 — spécification de développement

Statut : développement sur la branche `develop/v2`. Ne pas publier sur `main` avant validation.

## Sécurité et reprise
- Branche de sauvegarde V1 : `backup/v1-before-v2-2026-11-23`.
- Ne jamais écraser les données historiques de `public.hu_records`.
- Prévoir un export JSON local et une migration non destructive, testée avant bascule.
- Authentification et RLS par utilisateur ; aucune clé secrète côté navigateur.
- Quiz IA : fournisseur et coûts à définir, appels serveur uniquement.

## Architecture
Accueil calendrier mensuel ; navigation vers Piliers, Objectifs, Évolution, Paramètres ; ajout rapide permanent.
Calendrier : activités nommées et résultats visibles ; états réussite / échec / attente / neutre. Une activité passée non renseignée reste en attente. Mobile : grille mensuelle défilante horizontalement.

## Corps
Journal sportif rapide avec champs avancés optionnels selon discipline ; records ; défis libres ; étapes et séances préparatoires libres ; modèles facultatifs ; récupération.
Marathon cible : 19 septembre 2027, à enregistrer par l'utilisateur ou migrer depuis ses données.

## Esprit
Journal privé ; habitudes exclusivement à fréquence hebdomadaire sans jours fixes ; défis mentaux libres ; humeur et énergie facultatives. Aucun jour non pratiqué n'est un échec.

## Intelligence
Notes organisées, parcours d'apprentissage, livres et ressources, quiz générés à partir des notes et révision des erreurs. Ne pas inventer une génération IA opérationnelle sans intégration vérifiée.

## Finances
Deux espaces séparés : personnel (revenus réellement perçus, dépenses, épargne, patrimoine, dettes) et entreprises (CA, charges, résultat, trésorerie, objectifs). Plusieurs entreprises ; aucune assimilation du CA au revenu personnel. Saisie manuelle initiale.

## Objectifs et statistiques
Objectifs libres avec étapes et échéances facultatives ; mesures automatiques si liées à des résultats et jalons manuels. Statistiques excluant les activités en attente du taux de réussite. Bilans mensuels facultatifs.

## Plan d'implémentation
1. Construire prototype V2 indépendant dans `v2/`, sans modifier V1.
2. Définir modèle de données compatible et migration réversible.
3. Implémenter fonctionnalités des quatre piliers et calendrier.
4. Brancher synchronisation Supabase et vérifier RLS et restauration.
5. Tester mobile/ordinateur, puis demander validation avant publication.
