# Projet LabVIEW – Acquisition Température pour l’Estimation du Time-to-Live (TTL) d’un Moteur d’Avion

## 🔍 Objectif

Ce projet vise à développer une application LabVIEW permettant de simuler l'acquisition en temps réel des températures mesurées **en amont** et **en aval** d’un moteur d’avion. Ces données sont essentielles pour estimer le **Time-to-Live (TTL)** du moteur à l’aide de techniques de **Deep Learning**.

L’application permet à l’utilisateur de :
- visualiser les températures en **temps réel**,
- **enregistrer** les mesures dans un fichier CSV toutes les **500 ms**,
- arrêter l’acquisition via un bouton **STOP**.

---

## 🛠 Matériel et Simulation

### Éléments simulés :
- Deux capteurs **LM35**
- Carte **NI DAQ6008** *(non utilisée ici – simulation uniquement)*
- Logiciel **LabVIEW**

### Simulation dans LabVIEW :
- Utilisation des blocs **Simulate Signal** pour créer deux signaux sinusoïdaux simulant les températures.
- Affichage en temps réel avec un **Waveform Chart**.
- Exportation automatique dans un fichier CSV.

---

## ⚙️ Fonctionnement du Capteur LM35

Le **LM35** est un capteur analogique linéaire qui fournit une tension **proportionnelle à la température** :

```
10 mV/°C
```

### Exemple :
| Température (°C) | Tension (mV) |
|------------------|--------------|
| 25               | 250          |
| 50               | 500          |

### Conversion :
```
Température (°C) = Tension (V) X 100
```

Le capteur LM35 est simple, précis, et largement utilisé dans les systèmes embarqués.

---

## 🧪 Justification de la Simulation

Faute de disponibilité des capteurs physiques LM35 et de la carte NI DAQ6008, la simulation a été réalisée avec les blocs **Simulate Signal**. Cela permet :
- de reproduire le comportement réel du système,
- de valider l’architecture logicielle,
- de visualiser les résultats dans LabVIEW et d’exporter les données.

---

## 📊 Fonctionnalités de l’Application

| Fonction                     | Description                                                                 |
|------------------------------|-----------------------------------------------------------------------------|
| Acquisition simulée          | Deux signaux sinusoïdaux pour les températures amont et aval                |
| Intervalle d’acquisition     | 500 millisecondes                                                           |
| Affichage temps réel         | Deux courbes affichées sur un **Waveform Chart**                            |
| Export CSV automatique       | Données enregistrées dans `temperature_results.csv`                         |
| Bouton STOP                  | Permet à l’utilisateur d’arrêter l’acquisition manuellement                 |

---

## 💾 Fichier CSV généré

Le fichier `temperature_results.csv` contient les températures séparées par `;` :

```csv
Température Amont (°C);Température Aval (°C)
45.000;40.000
45.753;40.628
46.499;41.253
...
52.608;49.511
```

🗂️ **Emplacement** :  
Le fichier est **automatiquement sauvegardé dans le dossier de l’utilisateur**, par défaut sur le **Bureau** (`Desktop`).  
Cela permet un accès rapide et pratique aux résultats après l’exécution du VI.

---

## ▶️ Instructions d’Utilisation

1. Ouvrir le fichier `.vi` dans LabVIEW.
2. Cliquer sur **Run** pour lancer l’acquisition.
3. Observer les températures en temps réel sur le graphique.
4. Les données sont automatiquement enregistrées toutes les 500 ms dans `temperature_results.csv`.
5. Cliquer sur **STOP** pour arrêter l’acquisition.

---

## 📸 Captures d’écran

### 🧠 Block Diagram :

![Block Diagram](https://github.com/user-attachments/assets/b7c3323e-0ce8-46c1-aa2e-caad5491a63c)


### 👁️ Interface utilisateur (Front Panel) :

![Front Panel](https://github.com/user-attachments/assets/81680d21-51a4-41a5-9a2e-f4d3f8e98b1d)


---

## 👨‍💻 Auteur

**Youssef Essalihi**  
2A GI – Projet : Simulation de l’acquisition de températures dans le cadre de la prédiction du TTL moteur  
Juillet 2025

---

## 📌 Remarques finales

- Ce projet est un prototype simulé.
- Il peut être facilement adapté à un système réel avec NI DAQ6008 et capteurs LM35.
- Il constitue une base fiable pour une **future intégration Deep Learning** pour la prédiction du Time-to-Live.
