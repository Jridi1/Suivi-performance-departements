# 📊 Suivi de la Performance des Départements – Projet Power BI

Ce projet Power BI permet de visualiser et d’analyser la performance mensuelle de plusieurs départements pour l’année 2023. Il met l’accent sur la comparaison entre les objectifs et les résultats réalisés, le suivi d’indicateurs clés de performance (KPI), et la présentation des informations dans un tableau de bord clair et interactif adapté aux besoins métier.

---

## 🧾 Jeu de Données

Les données utilisées dans ce projet ont été créées manuellement pour simuler un environnement métier réaliste. Elles comprennent :

- **Date** : Premier jour de chaque mois en 2023 (de janvier à décembre)
- **Département** : Unités simulées (Ventes, Marketing, RH, IT, Finance)
- **Objectif** : Valeur cible mensuelle définie pour chaque département
- **Réalisé** : Valeur effectivement atteinte par chaque département

Une table de calendrier a été générée directement dans Power BI via DAX pour permettre les découpages temporels et les fonctions d’intelligence temporelle.

---

## ⚙️ Fonctionnalités

- **Cartes KPI** :
  - Total Réalisé
  - Objectif Total
  - % de Réalisation (avec formatage en pourcentage)
  - Écart de Performance (optionnel)

- **Vue Matricielle** :
  - % de Réalisation par Département et Mois (de Jan à Déc)
  - Tri chronologique correct via la colonne `MonthNumber`
  - Mise en forme conditionnelle pour mettre en évidence les sous/sur-performances

- **Graphiques** :
  - **Graphique en barres** : Comparaison mensuelle Réalisé vs Objectif
  - **Graphique en ligne** : Évolution des performances réalisées
  - **Graphique en colonnes** : Écart de performance par département

- **Filtres (Slicers)** :
  - Par Département
  - Par Mois

---

## 📐 Outils Utilisés

- Power BI Desktop (Microsoft)
- DAX pour les mesures et calculs
- Excel (préparation initiale des données)

---

## 🧠 Mesures DAX Clés

```DAX
Total Objective = SUM(PerformanceData[Objective])
Total Realized = SUM(PerformanceData[Realized])
% Realization = DIVIDE([Total Realized], [Total Objective])
Performance Gap = [Total Realized] - [Total Objective]
```

---

## 🧱 Calendar Table

A dedicated Calendar table was created using the following DAX:

```DAX
Calendar = 
ADDCOLUMNS(
    CALENDAR(DATE(2023,1,1), DATE(2023,12,31)),
    "Year", YEAR([Date]),
    "Month", MONTH([Date]),
    "MonthName", FORMAT([Date], "MMM"),
    "MonthNumber", MONTH([Date]),
    "YearMonth", FORMAT([Date], "YYYY-MM"),
    "Quarter", "T" & FORMAT([Date], "Q"),
    "Day", DAY([Date])
)
```

This table allows for chronological sorting of months and accurate slicing by time periods.

---

## 🧩 Fichiers Inclus

- `Sample.xlsx` – Données simulées
- `Projet.pbix` – Fichier Power BI
- `README.md` – Présentation du projet
- `Aperçu.pdf` – Aperçu du tableau de bord

---

## 📐 Conception du Tableau de Bord

- Filtres (Slicers) en haut à gauche (Département, Mois)
- Cartes KPI situées sous les filtres
- Visualisations principales à droite
- Mise en forme conditionnelle dans la matrice pour indiquer les performances
---

## 📬 Contact

**Abderrahim Jridi**  
Email: jeridi.abderahim@gmail.com  
LinkedIn: [abderrahim-jridi](https://www.linkedin.com/in/abderrahim-jridi/)

---

## 🚀 Améliorations Futures

- Ajouter des comparaisons annuelles (par exemple : avec des données fictives pour 2022)
- Créer des vues hiérarchiques (drill-down) des KPIs
- Publier le rapport sur Power BI Service pour partage ou intégration
---

![Dashboard Preview](./screenshot.png)
