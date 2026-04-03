# 🚀 INSTALLATION — Application PROPREV Équipe
## Guide étape par étape — environ 30 minutes

---

## ÉTAPE 1 — Créer un compte GitHub (5 min)

1. Va sur **github.com**
2. Clique **Sign up** (s'inscrire gratuitement)
3. Choisis un nom d'utilisateur (ex: proprev-formation)
4. Valide ton email

---

## ÉTAPE 2 — Créer le projet sur GitHub (5 min)

1. Une fois connecté, clique le **+ vert** en haut à droite → **New repository**
2. Nom du dépôt : `proprev-team-app`
3. Laisse tout par défaut, clique **Create repository**
4. Clique **uploading an existing file**
5. **Glisse-dépose tous les fichiers** de ce dossier :
   - `index.html`
   - `vercel.json`
   - Le dossier `api/` avec `chat.js` dedans
6. Clique **Commit changes** (bouton vert en bas)

---

## ÉTAPE 3 — Créer la base de données Firebase (10 min)

### 3.1 Créer le projet
1. Va sur **console.firebase.google.com**
2. Connecte-toi avec un compte Google (Gmail)
3. Clique **Créer un projet**
4. Nom : `proprev-team`
5. Désactive Google Analytics (pas besoin)
6. Clique **Créer le projet**

### 3.2 Créer la base de données
1. Dans le menu gauche, clique **Firestore Database**
2. Clique **Créer une base de données**
3. Choisis **Mode test** (permet l'accès libre — OK pour usage interne)
4. Choisis la région : **eur3 (Europe)** → Suivant → Terminé

### 3.3 Récupérer la configuration
1. Dans le menu gauche, clique l'icône ⚙️ (engrenage) → **Paramètres du projet**
2. Dans la section "Vos applications", clique **</>** (icône web)
3. Nom de l'app : `proprev-web` → Enregistrer l'application
4. **COPIE le bloc `firebaseConfig`** qui apparaît — il ressemble à ça :
```javascript
const firebaseConfig = {
  apiKey: "AIzaSy...",
  authDomain: "proprev-team.firebaseapp.com",
  projectId: "proprev-team",
  storageBucket: "proprev-team.appspot.com",
  messagingSenderId: "123456789",
  appId: "1:123456789:web:abc123"
};
```

### 3.4 Coller la config dans index.html
1. Ouvre le fichier `index.html` avec un éditeur de texte (Bloc-notes, Notepad++)
2. Cherche la ligne : `apiKey: "REMPLACE_PAR_TON_API_KEY"`
3. **Remplace TOUT le bloc firebaseConfig** par celui que tu as copié
4. Sauvegarde le fichier

---

## ÉTAPE 4 — Récupérer ta clé API Anthropic

1. Va sur **console.anthropic.com**
2. Connecte-toi avec ton compte
3. Clique **API Keys** dans le menu gauche
4. Clique **Create Key**
5. Nom : `proprev-app`
6. **COPIE la clé** (elle commence par `sk-ant-...`)
7. Garde-la précieusement — tu ne pourras plus la revoir

---

## ÉTAPE 5 — Déployer sur Vercel (5 min)

1. Va sur **vercel.com**
2. Clique **Sign up** → **Continue with GitHub**
3. Autorise Vercel à accéder à GitHub
4. Clique **Add New Project**
5. Trouve `proprev-team-app` dans la liste → clique **Import**
6. Laisse tout par défaut
7. **AVANT de cliquer Deploy**, clique **Environment Variables** :
   - Clique **Add**
   - Nom : `ANTHROPIC_API_KEY`
   - Valeur : colle ta clé `sk-ant-...`
   - Clique **Save**
8. Clique **Deploy** → attends 2 minutes

---

## ÉTAPE 6 — Accéder à l'application

Une fois le déploiement terminé, Vercel te donne une URL du type :
**`https://proprev-team-app.vercel.app`**

👉 **C'est cette URL que tu partages avec toute ton équipe.**
Chacun peut se connecter depuis n'importe quel ordinateur ou téléphone.

---

## ⚙️ Si tu veux personnaliser l'URL

1. Dans Vercel → ton projet → **Settings** → **Domains**
2. Tu peux ajouter un domaine personnalisé (ex: `equipe.proprev.fr`)
3. Ou garder l'URL Vercel gratuite — ça marche très bien

---

## ❓ En cas de problème

- **Erreur Firebase** : vérifie que le bloc firebaseConfig est bien collé dans index.html
- **Claude ne répond pas** : vérifie que la clé ANTHROPIC_API_KEY est bien dans Vercel → Settings → Environment Variables
- **Page blanche** : dans Vercel → ton projet → clique **Redeploy**

---

## 📱 Sur mobile (iPhone / Android)

L'application est responsive. Pour l'ajouter à l'écran d'accueil :
- **iPhone** : Safari → bouton partager → "Sur l'écran d'accueil"
- **Android** : Chrome → menu ⋮ → "Ajouter à l'écran d'accueil"

---

*Guide généré le 03/04/2026 — PROPREV FORMATION*
