# 🛠️ **Grafana-Loki-Setup**

[![Grafana](https://img.shields.io/badge/Grafana-FF9800?style=flat-square&logo=grafana&logoColor=white)](https://grafana.com/)  
[![Loki](https://img.shields.io/badge/Loki-00BFFF?style=flat-square&logo=grafana&logoColor=white)](https://grafana.com/oss/loki/)  
[![Promtail](https://img.shields.io/badge/Promtail-228B22?style=flat-square&logo=grafana&logoColor=white)](https://grafana.com/docs/loki/latest/clients/promtail/)  
[![Prometheus](https://img.shields.io/badge/Prometheus-E6522C?style=flat-square&logo=prometheus&logoColor=white)](https://prometheus.io/)

![Banner](img/background.png)

---

## 📄 **Description**

Ce repository propose une configuration complète pour la collecte, l'analyse et la visualisation des logs avec **Grafana**, **Loki**, **Promtail** et **Prometheus**. Il inclut des guides détaillés d’installation et de configuration, des exemples de dashboards et des configurations prêtes à l'emploi pour déployer une solution efficace de gestion des logs.

---

## 📂 **Contenu du Repository**

- **`doc/`** : Documentation détaillée des étapes d’installation et des configurations.
- **`img/`** : Images et illustrations pour les guides et dashboards.
- **`loki-config.yaml`** : Configuration de Loki pour l'agrégation des logs.
- **`promtail-config.yaml`** : Configuration de Promtail pour l’envoi des logs vers Loki.
- **`prometheus-config.yaml`** : Configuration de Prometheus pour le monitoring des métriques.
- **`dashboards/`** : Dashboards Grafana préconfigurés pour visualiser les logs.
- **`README.md`** : Guide détaillé du projet.

---

## ⚙️ **Prérequis**

- **Docker** et **Docker Compose** installés.
- Accès administrateur sur le système.

---

## 🚀 **Installation**

### 1. **Cloner le repository**

```bash
git clone https://github.com/ton_nom_utilisateur/grafana-loki-setup.git
cd grafana-loki-setup
```

### 2. **Lancer les services avec Docker Compose**

```bash
docker-compose up -d
```

### 3. **Accéder à Grafana**

Ouvre [http://localhost:3000](http://localhost:3000) dans ton navigateur.

- **Identifiants par défaut :**  
  - **Utilisateur :** `admin`  
  - **Mot de passe :** `admin`

---

## 🔧 **Configuration des Outils**

### 📏 **Loki**

Fichier de configuration : `loki-config.yaml`

Exemple de lancement avec Docker :

```bash
docker run -d --name loki -p 3100:3100 -v $(pwd)/loki-config.yaml:/etc/loki/config.yaml grafana/loki:2.9.7
```

### 📏 **Promtail**

Fichier de configuration : `promtail-config.yaml`

Exemple de lancement avec Docker :

```bash
docker run -d --name promtail -v $(pwd)/promtail-config.yaml:/etc/promtail/config.yaml grafana/promtail:2.9.7
```

### 📏 **Prometheus**

Fichier de configuration : `prometheus-config.yaml`

Exemple de lancement avec Docker :

```bash
docker run -d --name prometheus -p 9090:9090 -v $(pwd)/prometheus-config.yaml:/etc/prometheus/prometheus.yml prom/prometheus
```

---

## 📊 **Dashboards Grafana**

Pour importer les dashboards dans Grafana :

1. Accède à **Dashboards** → **Import**.
2. Sélectionne le fichier `.json` dans le dossier **`dashboards/`**.
3. Configure la source de données Loki et Prometheus.

---

## 📢 **Alertes et Notifications**

### ⚡ **Configurer un Webhook Discord**

1. Crée un webhook dans ton serveur Discord.
2. Dans Grafana, va dans **Alerting** → **Contact points**.
3. Ajoute un **nouveau contact point** avec l’URL du webhook.

---

## 📦 **Technologies Utilisées**

- **Grafana** : Visualisation et analyse des métriques et logs.
- **Loki** : Agrégation et stockage des logs.
- **Promtail** : Collecte et envoi des logs vers Loki.
- **Prometheus** : Monitoring des métriques.
- **Docker** : Conteneurisation des services.

---

## 📧 **Contact**

Pour toute question ou contribution, contacte **ton_nom_utilisateur** via GitHub.

---

## 📛 **Licence**

Ce projet est sous licence MIT. Voir le fichier [LICENSE](LICENSE) pour plus d’informations.

---

### 🗓 **Date de Création**

Décembre 2024
