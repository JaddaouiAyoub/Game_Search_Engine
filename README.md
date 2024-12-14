# Guide pour Exécuter le Projet
Description du Projet

Ce projet est un moteur de recherche de jeux vidéo basé sur l'indexation et la recherche d'informations. Il utilise un backend développé avec FastAPI pour traiter les requêtes de recherche et gérer la base de données, et un frontend construit avec Node.js pour afficher les résultats. Le système évalue également la pertinence des requêtes via des matrices de confusion générées automatiquement.
## Prérequis
- **Python 3.x** doit être installé sur votre machine.
- **Node.js** et **npm** doivent être installés pour le frontend.
- **Dépendances Python pour le backend :**
   - `fastapi`
   - `pymongo`
   - `nltk`
   - `pydantic`
   - `python-multipart`

Pour installer les dépendances, exécutez :
```bash
pip install -r requirements.txt
```

---

## 1. Configuration du Backend

1. Ouvrez un terminal et accédez au dossier `backend` :
   ```bash
   cd backend
   ```
2. Remplissez la base de données avec les données du fichier `rawg_games.json` en exécutant :
   ```bash
   python DataProcessing.py
   ```

> **Note :** Assurez-vous que le fichier `rawg_games.json` est bien présent dans le dossier `backend`.

---

## 2. Configuration du Frontend

1. Ouvrez un nouveau terminal et accédez au dossier `frontend` :
   ```bash
   cd frontend
   ```
2. Installez les dépendances nécessaires pour le frontend avec :
   ```bash
   npm install
   ```

---

## 3. Exécution du Projet

Une fois les étapes précédentes terminées :
1. Retournez dans le dossier racine du projet.
2. Lancez le projet en exécutant le fichier `run_servers.py` :
   ```bash
   python run_servers.py
   ```
   Cela démarrera le serveur backend ainsi que le serveur frontend.

---

## 4. Évaluation de la Recherche

Pour effectuer une évaluation des requêtes de recherche :
1. Exécutez le fichier `evaluate_search.py` dans le dossier racine :
   ```bash
   python evaluate_search.py
   ```
2. Les matrices de confusion générées par l'évaluation seront stockées dans le dossier `data`.

---

## Structure du Projet

```
project-root/
├── backend/
│   ├── __pycache__/
│   ├── api.py
│   ├── DataProcessing.py
│   ├── rawg_games.json
│   └── ...
├── frontend/
│   ├── src/
│   │   ├── components/
│   └── ...
├── evaluate_search.py
├── run_servers.py
├── requirements.txt
└── data/
```

---

## Notes
- Assurez-vous que les ports nécessaires pour le backend et le frontend sont disponibles.
- En cas de problèmes avec l'installation des dépendances ou l'exécution, vérifiez les versions des outils requis (Python, Node.js, npm).
- Les bibliothèques **nltk** nécessitent un téléchargement préalable des données. Cela est géré automatiquement par le projet.

Bonne utilisation !