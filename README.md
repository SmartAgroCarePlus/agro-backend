# 🌿 Agro-Backend - Microservice Principal  
**Cœur de l'architecture SmartAgroCare** : Gère les utilisateurs, orchestre les microservices et sert l'application mobile.  

---

## 📌 Description Technique  

### **Objectifs**  
1. **Authentification** : Gestion des utilisateurs (JWT)  
2. **Orchestration** : Routage des requêtes entre mobile/IA/vision  
3. **Data Hub** : Stockage PostgreSQL des diagnostics
4. **Inscription** sécurisée avec vérification d’email
5. **Récupération** des informations de profil
6. **API Gateway** : Point d'entrée unique pour le mobile  

### **Stack**  
- **Framework** : Flask + SQLAlchemy  
- **Base de données** : PostgreSQL  
- **Communication** :  
  - REST pour le mobile  
  - RabbitMQ pour l'IA (optionnel)  
- **Sécurité** : JWT, HTTPS, Rate Limiting  

---

## 🚀 Démarrage Rapide  

### Prérequis  
- Python 3.10+  
- PostgreSQL 14+  
- Redis (pour le cache)  

```bash
# 1. Cloner le dépôt
git clone https://github.com/SmartAgroCare/agro-backend.git

# 2. Configurer l'environnement
cp .env.example .env  # Remplir les variables

# 3. Installer & lancer
pip install -r requirements.txt
flask db upgrade  # Migrations
flask run --port=5000
```

## 🏗 Structure du Projet
```
agro-backend/
├── app/
│   ├── __init__.py       # Configuration Flask
│   ├── models/           # SQLAlchemy models
│   │   ├── user.py
│   │   └── diagnosis.py
│   ├── routes/
│   │   ├── auth.py       # /login, /register
│   │   ├── scan.py       # /scan, /history
│   │   └── admin.py      # Gestion des utilisateurs
│   ├── services/
│   │   ├── ia_client.py  # Appels à agro-ai
│   │   └── vision.py     # Appels à agro-vision
├── migrations/           # Alembic migrations
└── tests/
    ├── test_auth.py
    └── test_scan.py
```
