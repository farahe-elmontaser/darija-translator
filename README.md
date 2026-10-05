# 🇲🇦 Traducteur Darija - Extension Chrome

Extension Chrome pour traduire l'anglais vers le darija marocain avec reconnaissance vocale.

---

## 📺 Démonstration
**Vidéo :** https://drive.google.com/file/d/1InXKrC1oQUhz3mWwfXdVfqLo3JjnOWPh/view?usp=drive_link

---

## ✨ Fonctionnalités

- 🔄 **Traduction** : Anglais → Darija
- 🎤 **Reconnaissance vocale** : Parlez en anglais
- 🔊 **Lecture audio** : Écoutez en arabe
- 📋 **Extraction de texte** : Depuis n'importe quelle page web
- ⚙️ **Configuration** : URL API personnalisable

---

## 🚀 Installation

1. Ouvrez Chrome : `chrome://extensions/`
2. Activez **Mode développeur**
3. Cliquez **"Charger l'extension non empaquetée"**
4. Sélectionnez le dossier de l'extension

---

## 💻 Utilisation

### Traduction simple
1. Cliquez sur l'icône de l'extension
2. Tapez du texte en anglais
3. Cliquez **"Translate to Darija"**

### Avec la voix
1. Cliquez **"🎤 Speak in English"**
2. Parlez en anglais
3. La traduction apparaît automatiquement
4. Cliquez **"🔊 Read Aloud"** pour écouter

---

## ⚙️ Configuration

**Paramètres par défaut :**
```
API URL: http://localhost:8080/DarijaTranslatorService-1.0-SNAPSHOT/api/translator/translate
Username: translator
Password: password123
```

Pour modifier : Cliquez sur **⚙️** dans le side panel.

### 🔑 Clé API Gemini (backend)

Le service Java lit la clé Google Gemini depuis la variable d'environnement `GEMINI_API_KEY` (elle n'est jamais stockée dans le code) :

```bash
# Linux / macOS
export GEMINI_API_KEY="votre_cle"
# Windows (PowerShell)
$env:GEMINI_API_KEY="votre_cle"
```

Obtenez une clé gratuite sur [Google AI Studio](https://aistudio.google.com/apikey), puis redémarrez le serveur d'application.

---

## 🏗️ Architecture

```
Extension Chrome ──HTTP POST──> Service REST Java ──API──> Google Gemini
     (Client)         (JSON)        (JAX-RS + Jetty)              (AI)
```

**Technologies :**
- Chrome Extension Manifest V3
- Web Speech API (reconnaissance + synthèse)
- Fetch API (requêtes REST)
- Java + JAX-RS (backend)

---

## 📁 Fichiers

```
├── manifest.json       # Configuration
├── sidepanel.html      # Interface
├── sidepanel.css       # Styles
├── sidepanel.js        # Logique
├── background.js       # Service worker
└── icons/              # Icônes
```

---

## 🐛 Problèmes courants

| Problème | Solution |
|----------|----------|
| Erreur 404 | Vérifiez l'URL API dans les paramètres |
| Erreur 401 | Vérifiez username/password |
| Micro ne marche pas | Autorisez le microphone dans Chrome |
| Pas de son | Installez des voix arabes sur votre OS |

---

## 🎓 Projet académique

**Cours :** Web Services REST  
**Objectif :** Démontrer l'utilisation de services REST avec clients multiples  
**Version :** 2.0.0

**Concepts démontrés :**
- Architecture REST (stateless, JSON, HTTP)
- Interopérabilité (PHP + Chrome Extension)
- Intégration API externe (Google Gemini)
- APIs Web modernes (Speech Recognition, TTS)

---

**Développé pour le cours Web Services 2024-2025**
