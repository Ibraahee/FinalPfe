# ☕ CoffeeBI PT47 — Projet Final Intégré
## Tout en FastAPI — Un seul backend

---

## ⚠️ ÉTAPE 1 — Copier le modèle ML (Hajar)

```bash
copy C:\Users\hajou\OneDrive\Bureau\model_cafe.pkl coffeebi\backend\
```

---

## 🚀 ÉTAPE 2 — Lancer le backend FastAPI

```bash
cd coffeebi/backend
pip install -r requirements.txt
uvicorn main:app --reload --port 8000
```

✅ API disponible sur : http://localhost:8000
📖 Documentation : http://localhost:8000/docs

---

## 🚀 ÉTAPE 3 — Lancer le frontend React (Hafsa)

```bash
cd coffeebi/frontend
npm install
npm run dev
```

✅ Dashboard sur : http://localhost:5173

---

## 📡 Routes ML disponibles (Hajar)

| Route | Méthode | Description |
|---|---|---|
| `/api/predictions/predict` | POST | Prédiction prix unique (R²=1.0) |
| `/api/predictions/upload-predict` | POST | Import CSV + prédiction masse + MySQL |
| `/api/predictions/history` | GET | Historique des prédictions |
| `/api/predictions/ml-status` | GET | Vérifier que model_cafe.pkl est chargé |

---

## ✅ Tester le modèle ML

Va sur http://localhost:8000/docs et teste :

**GET** `/api/predictions/ml-status`
→ Doit retourner `"status": "loaded"`

**POST** `/api/predictions/predict`
```json
{
  "coffee_id": 17,
  "hour": 10,
  "sale_date": "2024-06-15",
  "payment_id": 2
}
```

---

## 👥 Responsabilités claires

| Fichier | Responsable |
|---|---|
| `backend/routes/predictions.py` | **Hajar** (logique ML) + **Abdelhadi** (structure route) |
| `backend/model_cafe.pkl` | **Hajar** |
| `backend/main.py` | **Abdelhadi** |
| `backend/database.py` | **Abdelhadi** |
| `backend/models/` | **Khadija** (schema) + **Abdelhadi** (ORM) |
| `frontend/` | **Hafsa** (aucun changement) |
| Power BI | **Ibrahim** |
| Documentation | **Ismail** |
