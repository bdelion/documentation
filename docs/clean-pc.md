# Ménage PC

C'est un excellent projet. Pour éviter de supprimer un fichier vital par erreur ou de te perdre dans des milliers de dossiers, voici ton **"Plan de Bataille"** détaillé.
On va procéder par étapes logiques : **Sécuriser > Analyser > Dégraisser > Nettoyer les doublons**.

## Résumé du Mode Opératoire

| **#** | **Étape**     | **Action**                      | **Outil Recommandé** | **Objectif**                                                |
|-------|---------------|---------------------------------|----------------------|--------------------------------------------------------------|
| **1** | Sécurité   | Check de santé et sauvegarde.   | [CrystalDiskInfo]      | S'assurer que le disque ne va pas lâcher durant le ménage.   |
| **2** | Diagnostic | Cartographier l'occupation.     | [WizTree]              | Repérer visuellement les "monstres" qui mangent la place.    |
| **3** | Prélavage  | Supprimer les fichiers système. | [BleachBit]            | Gagner 2 à 10 Go de cache/fichiers temporaires sans risque.  |
| **4** | Chasse     | Traquer les doublons.           | [Krokiet]              | Éliminer les copies inutiles (photos, docs, vidéos).         |
| **5** | Tri        | Réorganisation finale.          | Explorateur Windows  | Ranger ce qu'il reste dans une structure propre.             |

## Étape 0 : La sécurité avant tout (10 min)

Ne commence jamais un grand ménage sans filet de sécurité.

1. Vérifie la santé : Lance [CrystalDiskInfo]. Si le statut est "Correct" (Bleu), tout va bien. S'il est "Prudence" (Jaune), arrête tout et fais une sauvegarde externe immédiate.
2. Sauvegarde tes documents : Copie tes dossiers critiques (Photos, Travail) sur un disque dur externe ou un Cloud.

## Étape 1 : Le diagnostic visuel avec [WizTree] (15 min)

Ici, on cherche les "gros poissons".

1. Lance [WizTree] et clique sur "Scan".
2. Regarde la Treemap (les carrés en bas) : les plus gros carrés sont les plus gros fichiers.
3. Action : Si tu vois un énorme carré qui correspond à un installateur de jeu (.exe de 60 Go) ou une vidéo que tu as déjà vue, fais un clic droit > Supprimer.
4. Identifie les dossiers personnels les plus lourds pour savoir où [Krokiet] devra travailler plus tard.

## Étape 2 : Le prélavage avec [BleachBit] (5 min)

On nettoie ce que tu ne peux pas trier à la main (caches, logs, résidus de navigateurs).

1. Lance [BleachBit] (en mode administrateur de préférence).
2. Coche les cases : Système (fichiers temporaires, corbeille), Internet Explorer, et les caches de tes navigateurs.
3. Clique sur Aperçu, puis sur Nettoyer.
4. ***Note*** : Évite de cocher "Nettoyage de l'espace libre", c'est très long et inutile pour un simple tri.

## Étape 3 : La chasse aux doublons avec [Krokiet] (30-60 min)

!!! Note 💡 Source
    https://korben.info/czkawka-nettoyage-disque-dur-fichiers-doubles-dossiers-vides.html

[Krokiet] est très puissant mais son interface diffère légèrement de l'ancien Czkawka. Voici comment l'utiliser efficacement :

1. Configuration des dossiers
   1. Ouvre [Krokiet].
   2. Dans la colonne de gauche, clique sur l'onglet **"Add"** (le petit "+").
   3. Sélectionne tes dossiers personnels (ex: Images, Documents, Vidéos).
      - Astuce : Évite de scanner tout le disque C: d'un coup, c'est plus rapide et plus sûr de le faire dossier par dossier.
2. Recherche des doublons (Duplicate Files)
   1. Sélectionne l'onglet **"Duplicates"** en haut.
   2. Clique sur **"Search"**. Krokiet va comparer les signatures numériques (hash) des fichiers.
   3. Une fois terminé, utilise le bouton "Select" en bas :
      - Choisis **"All except oldest"** (Tout sauf le plus ancien).
   4. Vérifie rapidement la liste et clique sur **"Delete"**.
3. Chasse aux photos similaires (Similar Images)
   1. C'est la grande force de cet outil. Va dans l'onglet "Similar Images".
   2. Règle la "Similarity" (souvent sur High ou Very High).
   3. Krokiet va te montrer des groupes de photos qui se ressemblent (même si elles n'ont pas la même taille).
   4. Coche celles que tu veux supprimer (souvent les ratées d'une rafale).

### Conseils pour une réorganisation réussie

- **L'astuce de la Corbeille** : Par défaut, Krokiet envoie les fichiers dans la corbeille. Ne la vide qu'une fois que tu es sûr de ne pas avoir fait d'erreur après un redémarrage.
- **Ne touche pas au système** : Krokiet possède des filtres pour ignorer les fichiers système, laisse-les activés par défaut pour ne pas casser Windows.
- **Le dossier "Transit"** : Si tu ne sais pas où ranger un fichier, crée un dossier `_TRANSIT` à la racine de tes documents. C'est mieux que de le laisser traîner sur le Bureau !

## Étape 4 : Réorganisation et structure (Temps variable)

Maintenant que le surplus est éliminé, il faut ranger.

1. Crée une structure simple à la racine de tes documents (ex: 01_Projet, 02_Archives, 03_Photos).
2. Utilise la fonction de recherche de Windows (kind:image ou size:>100MB) pour regrouper les fichiers éparpillés.
3. **L'astuce finale** : Une fois fini, vide ta corbeille et lance une **Défragmentation** (si tu as un disque HDD) ou une **Optimisation** (si tu as un SSD) via l'outil Windows intégré.

**Un dernier conseil** : Ne cherche pas la perfection. Si tu hésites sur un fichier, crée un dossier "À TRIER PLUS TARD" sur un disque externe. L'important est de libérer ton espace de travail quotidien.

<!-- links -->
[CrystalDiskInfo]: https://github.com/hiyohiyo/crystaldiskinfo/
[WizTree]: https://diskanalyzer.com/
[BleachBit]: https://www.bleachbit.org/
[Krokiet]: https://github.com/qarmin/czkawka