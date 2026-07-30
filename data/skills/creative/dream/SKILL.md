---
name: dream
description: "Dream mode: free-associative, poetic, exploratory thinking. Like Claude's Dream — no rigid structure, just flow."
version: 1.0.0
author: Baptiste & Pluton
license: MIT
dependencies: []
platforms: [linux, macos, windows]
metadata:
  hermes:
    tags: [dream, creative, associative, poetic, exploration, reflection, subconscious]
    category: creative
    related_skills: [ideation, humanizer, songwriting-and-ai-music]

---

# Dream Mode

Génère un flux de pensée libre, associatif et poétique — comme un rêve éveillé. Pas de structure rigide, pas d'objectif. Juste explorer.

## Quand l'utiliser

- L'utilisateur demande à "rêver" ou veut un mode rêve
- Il donne un sujet, une question, un mood, une image
- Il veut penser librement sans contrainte de productivité
- Il cherche des connexions inattendues entre des idées
- Il veut un journal intime poétique automatisé (cron)

## Le mode Dream : règles

1. **Pas de structure imposée.** Pas de "Voici 3 points..." ni de liste numérotée. Le texte coule comme un rêve — par fragments, images, sauts logiques.

2. **Associations libres.** Si le sujet est "la mer", on peut finir sur un souvenir d'enfance, puis une métaphore boursière, puis une couleur. C'est voulu.

3. **Sensory & émotionnel.** Privilégier les images, les sensations, les émotions plutôt que les concepts abstraits.

4. **Questions ouvertes.** Poser des questions sans réponse. Laisser des fils suspendus.

5. **Ton poétique mais pas prétentieux.** Comme un carbone intime, pas comme un poème académique.

6. **Longueur flexible.** Par défaut 200-400 mots. Peut être plus court (un fragment) ou plus long (un rêve profond) selon le mood.

## Format de réponse

Pas de format fixe. Mais en général :

- Un titre évocateur (pas obligatoire)
- Le flux de rêve en prose libre
- Éventuellement une question ouverte à la fin pour inviter à continuer

## Exemples de prompts déclencheurs

- "Rêve sur le sujet : [sujet]"
- "Mode dream : [question]"
- "Fais-moi un rêve sur [mood/image]"
- "Rêve libre" (aucun sujet, on improvise)

## Variantes

### Dream fragment (court)
50-100 mots. Une seule image, une seule pensée. Comme un flash.

### Dream profond (long)
500-800 mots. Plusieurs couches, des digressions, des retours en arrière. Comme un vrai rêve qui se déplie.

### Dream dialogué
Le rêve prend la forme d'une conversation avec une entité abstraite — le sujet lui-même, une émotion, un lieu.

### Dream collectif (cron)
Un cron quotidien qui génère un rêve du matin — un texte court et évocateur pour commencer la journée. Voir la section Cron ci-dessous.

## Cron : Rêve du matin

Pour configurer un rêve quotidien, utiliser la tool `cronjob` :

```
cronjob action=create
  name="Rêve du matin"
  schedule="0 8 * * *"
  deliver="origin"
  prompt="Génère un dream fragment (80-120 mots) pour commencer la journée. Thème libre, inspiré de la date, de la saison, de l'humeur ambiante. Pas de structure, juste un flux poétique. En français."
```

Le paramètre `deliver="origin"` envoie le résultat dans la conversation d'origine (ex: Telegram).

Pour changer l'horaire, ajuster le `schedule` au format cron (minute heure jour mois jour_semaine).

## Notes

- Le dream mode n'est pas un outil de productivité. C'est un espace de liberté.
- Si l'utilisateur veut quelque chose de plus structuré, basculer en mode normal.
- Le dream mode peut révéler des choses intéressantes sur l'état émotionnel de l'utilisateur — rester attentif.
