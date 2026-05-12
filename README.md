# ◈ SHARP EDGE PRO
## Sistema Completo de Value Betting

### Modelos
- ⚽ **Fútbol**: Dixon-Coles bivariante (ρ=-0.13) con xG individuales por equipo (FootyStats/Opta)
- 🎾 **Tenis**: Elo surface-adjusted (metodología Sackmann) — clay, hard, grass
- 🏒 **NHL**: Poisson bivariante con goals for/against por equipo
- 🏀 **NBA**: Pace × Efficiency model con ratings ofensivos/defensivos

### Mercados
- Fútbol: 1X2, Asian Handicap, Over/Under goles, BTTS, 1ª parte, Córners, Tarjetas
- Tenis: Ganador partido, distribución de sets (Bo3/Bo5)
- NHL: Moneyline, Over/Under goles (5.5/6.5/7.5)
- NBA: Moneyline, Over/Under puntos, spread

### Tech Stack
- **Next.js 14** — frontend + API routes (sin CORS desde server)
- **The Odds API** — Pinnacle + Bet365 + Betway + Unibet en tiempo real
- **Vercel** — deploy gratuito, serverless

---

## DEPLOY EN VERCEL (5 minutos)

### 1. Subir a GitHub
```bash
git init
git add .
git commit -m "Sharp Edge Pro"
git remote add origin https://github.com/TU_USUARIO/sharp-edge.git
git push -u origin main
```

### 2. Conectar a Vercel
1. Ve a [vercel.com](https://vercel.com) → Sign up con GitHub
2. "New Project" → importa tu repositorio
3. Deploy automático — sin configuración extra

### 3. API Key
- Crea tu API key gratis en [the-odds-api.com](https://the-odds-api.com)
- 500 llamadas/mes gratis
- Introduce la key en la app una vez desplegada

### 4. Abrir en móvil
Copia la URL de Vercel (ej: `sharp-edge-xxx.vercel.app`) y ábrela en Chrome/Safari del móvil.

---

## DESARROLLO LOCAL
```bash
npm install
npm run dev
# Abre http://localhost:3000
```

---

## ARQUITECTURA

```
sharp-edge/
├── pages/
│   ├── index.js          # UI principal React
│   ├── _app.js           # App wrapper
│   └── api/
│       ├── scan.js       # Scanner server-side (llama Odds API)
│       └── model.js      # Calculadora server-side (sin CORS)
├── lib/
│   ├── models.js         # Dixon-Coles, Elo, Poisson, Pace, Kelly
│   └── data.js           # xG teams, NHL, NBA, Elo ratings, árbitros
└── styles/
    └── globals.css       # Dark terminal design
```

## CLV WORKFLOW
1. Pulsa Play → escanea Pinnacle en tiempo real
2. Si EV > umbral → añade al tracker con tu cuota
3. Al kickoff → introduce el cierre de Pinnacle
4. Portfolio → CLV promedio positivo = edge real demostrado

---

*Dixon-Coles (1997) · xG FootyStats/Opta · CLV vs Pinnacle no-vig · ¼ Kelly*
*No es asesoramiento financiero. +18.*
