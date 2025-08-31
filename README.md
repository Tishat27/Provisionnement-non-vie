# Provisionnement-non-vie



## 📦 Données

Les données utilisées proviennent du jeu d’exemple **`freclaimset2motor`** fourni par le package **CASdatasets** pour la formation en actuariat.

* **Claimset** : informations au niveau des sinistres individuels (paiements cumulés, recouvrements, provisions attendues).
* **Claimsummary** : synthèse annuelle par portefeuille (nombre de sinistres, exposition, primes émises).

Ces données représentent un portefeuille anonymisé d’assurance automobile et sont utilisées pour illustrer le calcul des provisions techniques.


---


## 🧠 Objectifs

L’objectif principal est d’étudier et comparer différentes méthodes de **projection des sinistres** :

* **Chain Ladder** (manuel et package R)
* **Mack Chain Ladder**
* **Bornhuetter-Ferguson (BF)**
* **Bootstrap Chain Ladder**

Les objectifs spécifiques sont :

1. Comprendre le fonctionnement interne des modèles et des facteurs de développement.
2. Vérifier les hypothèses de chaque méthode (indépendance, linéarité, variance).
3. Estimer les **réserves techniques** et quantifier l’incertitude associée.
4. Comparer les résultats manuels avec ceux fournis par les packages R standards.

## ⚙️ Technologies utilisées

* **Langage :** R
* **Packages principaux :** `ChainLadder`, `CASdatasets`, `dplyr`, `ggplot2`, `kableExtra`, `tinytex`
* **R Markdown / LaTeX :** Documentation et génération de rapports PDF

## 📈 Résultats

1. **Triangle de paiements** : construction et correction des incréments pour éliminer les doublons et valeurs négatives.
2. **Chain Ladder** : estimation manuelle des facteurs de développement et projection des paiements futurs.
3. **Mack Chain Ladder** : quantification de l’incertitude via MSEP et calcul des quantiles (75 % et 95 %).
4. **Bornhuetter-Ferguson** : combinaison de l’information historique et d’un loss ratio a priori pour obtenir des réserves plus robustes.
5. **Bootstrap Chain Ladder** : distribution empirique des réserves, avec moyenne, écart-type et quantiles.
6. **Validation** : comparaison des résultats manuels et des méthodes standards R, mise en évidence des écarts et de l’impact des hypothèses.

### Exemple de résultat clé

| Méthode              | Réserve totale (€) | Quantile 75 % (€) | Quantile 95 % (€) |
| -------------------- | ------------------ | ----------------- | ----------------- |
| Chain Ladder         | 13 222 270         | -                 | -                 |
| Mack CL              | 13 222 270         | 12 177 526        | 15 770 048        |
| Bornhuetter-Ferguson |13 472 077          | -                 | -                 |
| Bootstrap CL         |13 217 032          | 13 895 967        | 15 033 649        |

## 📁 Fichier principal

📍 `Notebook/Tarification non-vie.ipynb`

---

Si tu veux, je peux te rédiger **une version courte et percutante pour GitHub**, adaptée au format `README.md` avec badges et sections prêtes à l’emploi pour ton projet. Veux‑tu que je fasse ça ?
