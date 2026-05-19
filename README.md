# Commerciale TES — Sito web

Sito statico ottimizzato per Vercel.

## Deploy su Vercel — 3 modi (pick one)

### A. Vercel CLI (più veloce — 30 secondi)
```bash
npm i -g vercel    # solo la prima volta
cd dist            # entra in questa cartella
vercel             # segue il prompt → "Y" a tutto → Done.
vercel --prod      # promuove in produzione
```

### B. Drag & drop (zero CLI)
1. Vai su https://vercel.com/new
2. **"Other" → "Browse all templates" → "Deploy"** → trascina questa intera cartella `dist/`
3. Pulsante **"Deploy"** → attendi ~30 secondi
4. Vercel ti dà un URL `*.vercel.app` per testare

### C. Git (best practice per aggiornamenti continui)
1. `git init && git add . && git commit -m "initial"`
2. `git remote add origin <repo-url>` (GitHub/GitLab)
3. `git push -u origin main`
4. Su vercel.com → **"Add New Project"** → seleziona il repo → **Deploy**
5. D'ora in poi ogni `git push` deploya in automatico

## Dominio custom (commercialetes.it)
1. Project Settings → **Domains** → **Add** → `commercialetes.it`
2. Vercel ti mostra i record DNS da impostare presso il tuo registrar:
   - `A` record: `76.76.21.21`
   - `CNAME` `www`: `cname.vercel-dns.com`
3. Propagazione DNS: 5 minuti – 24 ore. HTTPS automatico.

## Struttura

```
dist/
├── index.html               ← homepage
├── image-slot.js
├── vercel.json              ← config: clean URLs, cache, security headers
├── robots.txt
├── sitemap.xml
├── assets/                  ← illustrazioni casi studio
├── blog/                    ← 5 articoli
├── legal/                   ← privacy, cookie, termini, checklist PDF
└── uploads/                 ← foto team
```

## Integrazioni lead

- **Formspree** (email) — configurato. ID nel `LEAD_CONFIG` dentro `index.html`.
- **HubSpot CRM** — non collegato. Puoi importare manualmente i lead dall'email.

## Aggiornamenti futuri
- Modifiche al sito → ridistribuire (sostituire i file su Vercel).
- Per il workflow Git: ogni push deploya automaticamente.
