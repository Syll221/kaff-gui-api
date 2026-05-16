# 🔧 Stack Technique Backend - Kàff GUI API

## Architecture & Framework

<div align="center">

### Core Framework
![Python](https://img.shields.io/badge/Python-3.12-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Django](https://img.shields.io/badge/Django-5.1-092E20?style=for-the-badge&logo=django&logoColor=white)
![Django REST Framework](https://img.shields.io/badge/DRF-3.15-ff1709?style=for-the-badge&logo=django&logoColor=white)

### Base de données
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-16-316192?style=for-the-badge&logo=postgresql&logoColor=white)
![psycopg](https://img.shields.io/badge/psycopg-3.2-336791?style=for-the-badge&logo=postgresql&logoColor=white)

</div>

---

## 🔐 Sécurité & Authentification

<div align="center">

![JWT](https://img.shields.io/badge/JWT-Tokens-000000?style=for-the-badge&logo=jsonwebtokens&logoColor=white)
![2FA](https://img.shields.io/badge/2FA-TOTP-4285F4?style=for-the-badge&logo=google-authenticator&logoColor=white)
![Argon2](https://img.shields.io/badge/Argon2-Hashing-00599C?style=for-the-badge&logo=security&logoColor=white)
![PyNaCl](https://img.shields.io/badge/PyNaCl-Encryption-FF6B6B?style=for-the-badge&logo=libsodium&logoColor=white)

**Sécurité OWASP Top 10**
- Django Axes (Brute-force protection)
- Django OTP (2FA TOTP)
- PyNaCl (libsodium sealed box)
- Argon2 (Password hashing)

</div>

---

## 📚 API & Documentation

<div align="center">

![OpenAPI](https://img.shields.io/badge/OpenAPI-3.0-6BA539?style=for-the-badge&logo=openapiinitiative&logoColor=white)
![Swagger](https://img.shields.io/badge/Swagger-UI-85EA2D?style=for-the-badge&logo=swagger&logoColor=black)
![drf-spectacular](https://img.shields.io/badge/drf--spectacular-0.28-ff1709?style=for-the-badge&logo=django&logoColor=white)

**Features**
- Auto-generated OpenAPI 3.0 schema
- Interactive Swagger UI
- Django Filter integration
- CORS headers support

</div>

---

## 📊 Observabilité & Logging

<div align="center">

![structlog](https://img.shields.io/badge/structlog-24.4-00ADD8?style=for-the-badge&logo=json&logoColor=white)
![JSON Logs](https://img.shields.io/badge/JSON-Logs-000000?style=for-the-badge&logo=json&logoColor=white)

**Structured Logging**
- django-structlog (Request/Response logging)
- JSON format pour parsing facile
- Contexte enrichi automatique

</div>

---

## 🚀 Production & Déploiement

<div align="center">

![Gunicorn](https://img.shields.io/badge/Gunicorn-23.0-499848?style=for-the-badge&logo=gunicorn&logoColor=white)
![WhiteNoise](https://img.shields.io/badge/WhiteNoise-6.8-00A98F?style=for-the-badge&logo=nginx&logoColor=white)
![Railway](https://img.shields.io/badge/Railway-Deploy-0B0D0E?style=for-the-badge&logo=railway&logoColor=white)

**Infrastructure**
- Gunicorn WSGI server
- WhiteNoise static files (Brotli compression)
- Railway V2 hosting
- PostgreSQL managed database

</div>

---

## 🧪 Qualité & Tests

<div align="center">

![pytest](https://img.shields.io/badge/pytest-8.3-0A9EDC?style=for-the-badge&logo=pytest&logoColor=white)
![mypy](https://img.shields.io/badge/mypy-1.13-2A6DB2?style=for-the-badge&logo=python&logoColor=white)
![Ruff](https://img.shields.io/badge/Ruff-0.8-D7FF64?style=for-the-badge&logo=ruff&logoColor=black)
![Bandit](https://img.shields.io/badge/Bandit-1.8-FFD43B?style=for-the-badge&logo=python&logoColor=black)

**Outils de qualité**
- **Ruff** - Linter & formatter ultra-rapide (remplace black + isort + flake8)
- **mypy** - Type checking strict
- **pytest** - Framework de tests
- **bandit** - Security linter (OWASP)
- **pre-commit** - Git hooks automatiques

</div>

---

## 📦 Dépendances Clés

<div align="center">

| Catégorie | Technologies |
|-----------|-------------|
| **Framework** | Django 5.1, DRF 3.15 |
| **Database** | PostgreSQL, psycopg 3.2 |
| **Auth** | JWT, Django OTP, PyNaCl, Argon2 |
| **API** | drf-spectacular, django-filter, CORS |
| **Security** | Django Axes, PyNaCl, Argon2 |
| **Logging** | structlog, django-structlog |
| **Production** | Gunicorn, WhiteNoise, Railway |
| **Quality** | Ruff, mypy, pytest, bandit |

</div>

---

## 🏗️ Architecture

```
┌─────────────────────────────────────────────────┐
│           Client (Mobile App)                    │
└─────────────────┬───────────────────────────────┘
                  │ HTTPS + JWT
┌─────────────────▼───────────────────────────────┐
│         Gunicorn WSGI Server                     │
│  ┌──────────────────────────────────────────┐   │
│  │      Django REST Framework               │   │
│  │  ┌────────────────────────────────────┐  │   │
│  │  │  Authentication Middleware         │  │   │
│  │  │  - JWT Validation                  │  │   │
│  │  │  - 2FA TOTP                        │  │   │
│  │  │  - Brute-force Protection          │  │   │
│  │  └────────────────────────────────────┘  │   │
│  │  ┌────────────────────────────────────┐  │   │
│  │  │  Business Logic (Apps)             │  │   │
│  │  │  - Users, Pigeons, Cages           │  │   │
│  │  │  - Couples, Reproductions          │  │   │
│  │  │  - Sorties, Dashboard              │  │   │
│  │  └────────────────────────────────────┘  │   │
│  └──────────────────────────────────────────┘   │
└─────────────────┬───────────────────────────────┘
                  │ psycopg 3.2
┌─────────────────▼───────────────────────────────┐
│         PostgreSQL Database                      │
│  - UUID Primary Keys                             │
│  - Soft Delete (deleted_at)                      │
│  - Timestamps (created_at, updated_at)           │
└──────────────────────────────────────────────────┘
```

---

## 🎯 Points Forts

<div align="center">

### ✅ Sécurité Banking-Grade
- Authentification 2FA obligatoire
- Chiffrement E2EE (PyNaCl sealed box)
- Protection brute-force (Django Axes)
- Hash Argon2 (OWASP recommandé)

### ✅ Performance
- Détection N+1 queries (django-zen-queries)
- Connection pooling (psycopg)
- Static files optimisés (WhiteNoise + Brotli)

### ✅ Maintenabilité
- Type checking strict (mypy)
- Linting automatique (Ruff)
- Tests automatisés (pytest)
- Documentation auto-générée (OpenAPI)

### ✅ Observabilité
- Logs structurés JSON
- Contexte enrichi automatique
- Traçabilité complète des requêtes

</div>

---

<div align="center">

## 🚀 Déployé sur Railway

![Railway](https://img.shields.io/badge/Status-Production-success?style=for-the-badge&logo=railway&logoColor=white)
![Python](https://img.shields.io/badge/Python-3.12-blue?style=for-the-badge&logo=python&logoColor=white)
![Django](https://img.shields.io/badge/Django-5.1-green?style=for-the-badge&logo=django&logoColor=white)

**API REST sécurisée et performante pour la gestion de volière**

</div>
