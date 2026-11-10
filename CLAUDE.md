# Application de covoiturage (Flutter)

## Stack
- Flutter stable, Dart 3.x
- Gestion d'état : Riverpod (flutter_riverpod + riverpod_annotation + riverpod_generator)
- Navigation : go_router
- Backend : à définir

## Architecture
lib/
core/        thème, routage, utilitaires
features/
<fonctionnalité>/
data/          accès aux données (API, base)
domain/        modèles et règles métier
presentation/  écrans, widgets, providers

## Règles Riverpod
- Utiliser les providers générés avec l'annotation @riverpod.
- Un provider par responsabilité, placé dans la couche presentation de sa fonctionnalité.
- Après avoir ajouté ou modifié un provider : dart run build_runner build --delete-conflicting-outputs
- Ne pas utiliser setState pour de l'état partagé entre écrans.

## Commandes de vérification
- dart format .
- flutter analyze
- flutter test

## Règles générales
- Avant de dire qu'une tâche est terminée : analyze et test doivent passer.
- Aucune clé d'API ou secret en dur dans le code.
- Position GPS : demander la permission, ne rien stocker sans consentement (RGPD).
- Petits commits, un message clair par fonctionnalité.