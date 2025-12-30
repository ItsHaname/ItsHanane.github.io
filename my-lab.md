---
layout: default
title: Mon laboratoire
nav: my-lab
---
# My Own Lab — Structure et pages
Voici une proposition de page qui transforme la "structure du lab" (que tu m'as fournie) en page web lisible et navigable.

## Vue d'ensemble
- Nom du labo : My Own Lab
- Objectif : s'exercer sur reconnaissance, exploitation, post-exploitation, persistence

## Topologie (exemple)
```text
MyOwnLab/
├─ network/
│  ├─ 10.10.10.0-24 (réseau)
│  ├─ web-server/
│  │  ├─ vulnerableservice (HTTP)
│  ├─ db-server/
│  │  ├─ postgres (privilege escalation)
├─ machines/
│  ├─ web-1.md
│  ├─ db-1.md
│  ├─ vm-windows.md
├─ writeups/
│  ├─ web-1-writeup.md
│  ├─ db-1-writeup.md
```

## Exemple de contenu machine (template)
- Nom : web-1
- IP : 10.10.10.10
- Objectif : trouver et exploiter une vulnérabilité XSS / LFI / RCE
- Indices : /admin route, version outdated
- Flags : user.txt, root.txt
- Write-up : lien vers writeup détaillé

---

Si tu veux, je transforme ta photo/structure exactement en pages (par ex. une page pour chaque machine). Envoie une photo claire de la structure ou copie le texte, et je génère automatiquement les fichiers Markdown pour chaque machine.
