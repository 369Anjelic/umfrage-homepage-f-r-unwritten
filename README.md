# 🚀 UNWRITTEN STUDIO - FEEDBACK HOMEPAGE

**Schnelle Umfrage-Homepage mit automatischer Email-Integration**

---

## ⚡ QUICK START (5 Minuten)

### 1️⃣ Formspree einrichten (kostenlos, keine Programmierung)

```bash
# Geh zu https://formspree.io
# Sign up (kostenlos)
# Erstelle ein neues Form
# Kopiere deine Form ID (sieht so aus: f/abc123xyz)
```

### 2️⃣ Form ID in index.html eintragen

Öffne `index.html` und finde diese Zeile:
```javascript
const API_ENDPOINT = 'https://formspree.io/f/YOUR_FORM_ID';
```

Ersetze `YOUR_FORM_ID` mit deiner echten ID, z.B.:
```javascript
const API_ENDPOINT = 'https://formspree.io/f/myzwvbra';
```

### 3️⃣ Deploy auf GitHub Pages (kostenlos)

```bash
# Terminal öffnen
cd unwritten-feedback-hub

# Git initialisieren (falls nicht bereits geschehen)
git init
git config user.email "your@email.com"
git config user.name "Your Name"

# Alles hinzufügen und committen
git add .
git commit -m "Initial Unwritten Feedback setup"

# GitHub
# 1. Erstelle neues Repo auf github.com: "unwritten-feedback"
# 2. Push lokal:
git remote add origin https://github.com/YOUR_USERNAME/unwritten-feedback.git
git branch -M main
git push -u origin main

# 3. GitHub Settings → Pages → Deploy from branch → main
# 4. Warte 1-2 Minuten
# 5. Deine URL: https://YOUR_USERNAME.github.io/unwritten-feedback
```

**FERTIG! 🎉**

---

## 🌐 ALTERNATIVE DEPLOYMENT OPTIONEN

### Option A: Netlify (EMPFOHLEN - Schneller)

```bash
# 1. Geh zu https://netlify.com
# 2. Sign up mit GitHub
# 3. "New site from Git"
# 4. Wähle dein unwritten-feedback Repo
# 5. Deploy!
# 
# Deine URL: https://[auto-name].netlify.app
# (kannst du später umbenennen)
```

### Option B: Vercel (SUPER SCHNELL)

```bash
# 1. Geh zu https://vercel.com
# 2. "New Project"
# 3. Importiere GitHub Repo
# 4. Deploy!
```

### Option C: Docker + Self-Hosted

```bash
# Dockerfile:
FROM node:18-alpine
WORKDIR /app
COPY index.html .
EXPOSE 8080
CMD ["npx", "http-server", "-p", "8080"]

# Build & Run:
docker build -t unwritten-feedback .
docker run -p 8080:8080 unwritten-feedback
```

---

## 📧 EMAIL SETUP (Wichtig!)

### Mit Formspree (EASIEST):

1. **Sign up** auf https://formspree.io (kostenlos)
2. **Erstelle ein Form** mit deiner Email
3. **Formspree sendet dir automatisch** alle Antworten
4. Du erhältst Email pro Feedback ✅

### Mit eigenem Email-Service:

Falls du Formspree nicht magst, nutze:
- **SendGrid** (50 free emails/day)
- **Mailgun** (10 free emails/day)
- **AWS SES** (super günstig)

Für diese Options brauchst du aber einen Backend-Server (Node.js, Python, etc.)

---

## 📊 WAS PASSIERT WENN JEMAND FEEDACK GIBT?

```
1. Person füllt Formular aus
2. Klickt "Feedback senden"
3. Formspree empfängt Daten
4. ✉️ Email landet in DEINEM Postfach
5. Person sieht "✅ Danke für dein Feedback"
6. Zusätzlich: Ergebnisse-Summary auf Seite
```

**Email sieht so aus:**
```
Von: noreply@formspree.io
Betreff: Neues Feedback von max@example.com

Entdeckung: Suchmaschine
Emotion: Inspiriert
Klarheit: 5/5
Design: 4/5
...
(alle 12 Fragen mit Antworten)
```

---

## 🎨 CUSTOMIZATION

### Homepage-Titel ändern:
In `index.html` finde:
```html
<h1>🌍 Unwritten Studio</h1>
```
Ersetze mit deinem Titel.

### Farben anpassen:
Suche nach `:root` im `<style>`:
```css
:root {
    --color-primary: #1e87d5;  /* Diese Farbe ändern */
    --color-bg: #0f172a;       /* Hintergrund */
    --color-success: #10b981;  /* Erfolgs-Grün */
}
```

Neue Farbe eingeben, z.B. `#FF6B6B` für Rot.

### Fragen ändern:
Jede Frage ist ein `<div class="form-group">` Block.  
Kopiere einen Block und modifiziere:
```html
<div class="form-group">
    <span class="question-number">13/12</span>
    <label>Deine neue Frage?</label>
    <div class="options">
        <div class="option">
            <input type="radio" id="q13_option1" name="q13" value="Option 1">
            <label for="q13_option1">📝 Option 1</label>
        </div>
    </div>
</div>
```

---

## 🔍 MONITORING & ANALYTICS

### Option 1: Formspree Dashboard
- Log in auf formspree.io
- Sieh alle Submissions live
- Download als CSV

### Option 2: Google Analytics (optional)
Füge zu `index.html` hinzu vor `</head>`:
```html
<script async src="https://www.googletagmanager.com/gtag/js?id=G-XXXXX"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());
  gtag('config', 'G-XXXXX');
</script>
```

(Ersetze `G-XXXXX` mit deiner Google Analytics ID)

---

## 🚨 TROUBLESHOOTING

### "Feedback wird nicht gesendet"
- ✅ Überprüfe, dass deine Form ID korrekt ist
- ✅ Öffne Browser-Console (F12) und schau nach Errors
- ✅ Versuche mit Test-Email

### "Ich erhalte keine Emails"
- ✅ Überprüfe Spam-Ordner
- ✅ Log in auf formspree.io und verifiziere deine Email
- ✅ Teste mit Test-Submission direkt auf formspree.io

### "Form sieht komisch aus"
- ✅ Cache leeren (Strg+Shift+Del)
- ✅ Hard Refresh (Strg+F5)
- ✅ Öffne in Private/Incognito Browser

### "Kann Git nicht pushen"
```bash
# Überprüfe, dass du am main branch bist:
git branch

# Wenn nicht:
git checkout -b main

# Oder force push:
git push -u origin main --force
```

---

## 📱 MOBILE RESPONSIVENESS

Die Seite ist **fully responsive**:
- ✅ Desktop (1920px+)
- ✅ Tablet (768px-1280px)
- ✅ Mobile (320px-767px)

Teste mit:
```bash
# Chrome DevTools: F12 → Toggle device toolbar (Strg+Shift+M)
```

---

## 🔐 DATENSCHUTZ & SICHERHEIT

- ✅ HTTPS verschlüsselt (wenn auf GitHub Pages/Netlify/Vercel)
- ✅ Keine Daten werden lokal gespeichert
- ✅ Formspree speichert verschlüsselt
- ✅ GDPR-konform (kein Tracking)

Falls gefordert, füge Datenschutz-Link hinzu:
```html
<a href="https://formspree.io/privacy">Datenschutz</a>
```

---

## 📈 NÄCHSTE SCHRITTE NACH DEPLOYMENT

1. **Teile die URL** mit Zielgruppe
   - Social Media posten
   - Newsletter
   - Webseite Link hinzufügen

2. **Sammle Feedback** (mindestens 50-100 Responses)

3. **Analysiere Daten** mit den Insights
   - Top Pain Points
   - NPS Scores
   - Showcase Interessen

4. **Iteriere Homepage** basierend auf Feedback

---

## 🎯 FILE STRUKTUR

```
unwritten-feedback-hub/
├── index.html          ← MAIN FILE (öffnen im Browser)
├── setup.sh            ← Optional Setup-Script
├── README.md           ← Diese Datei
└── .gitignore          ← Ignoriere bestimmte Dateien bei Git
```

**Das ist alles, was du brauchst!** Nur eine HTML-Datei, keine komplexen Dependencies.

---

## 💬 FRAGEN?

Falls etwas nicht funktioniert:

1. **Überprüfe Formspree**: Sind deine Submissions dort sichtbar?
2. **Check Console**: F12 → Console → Sieh nach roten Fehlern
3. **GitHub Issues**: Erstelle Issue im Repo
4. **Kontakt**: post@unwritten.studio

---

## 📞 QUICK LINKS

- **Formspree**: https://formspree.io
- **GitHub Pages Docs**: https://pages.github.com
- **Netlify Docs**: https://docs.netlify.com
- **Vercel Docs**: https://vercel.com/docs

---

**Version**: 1.0  
**Last Updated**: Januar 2026  
**Status**: ✅ READY TO DEPLOY

---

## 🎉 VIEL ERFOLG!

Dein Feedback wird dir helfen, die Unwritten Studio Homepage zu optimieren.

**Go live in 5 Minuten. Viel Spaß! 🚀**
