# TIMMY - Sustainable Plot Planner

TIMMY helps families, small builders, and community projects turn an irregular plot into a practical, climate-aware concept plan. It focuses on early site decisions - orientation, open space, rainwater, materials, and cost - before detailed architecture begins.

Built for **Nirmaan 2026** (National Level Tech Skill Expo) under the Sustainable Engineering theme.

**Team: Sentinel** · SISTec, Gandhi Nagar, Bhopal

| Member | Role |
|--------|------|
| MD Arshad Raza | Team Lead |
| Himanshu Mishra | Team Member |
| Ayush Kumar Singh | Team Member |
| Mohd Tousif Ansari | Team Member |
| Bhumika Dohle | Team Member |

---

## What it does

1. **Plot input** - Name, approximate area, road access direction, and location (search or GPS).
2. **Priorities** - Choose what matters: cooling, rainwater, green space, budget.
3. **Concept options** - Three ranked layout directions with short explanations.
4. **Cost sketch** - Editable local material rates and a rough built-up cost range.

This is a **plot-aware decision aid**, not a room generator or construction drawing. Recommendations are illustrative; a local architect or engineer should review soil, structure, setbacks, and approvals.

---

## Quick start

```bash
# Requires Node.js 18+
npm install
npm run dev
```

Open the URL shown in the terminal (usually `http://localhost:5173`).

| Command | Purpose |
|---------|---------|
| `npm run dev` | Local development server |
| `npm run build` | Production build → `dist/` |
| `npm run preview` | Serve the production build |
| `npm run typecheck` | TypeScript check |
| `npm run lint` | ESLint |

---

## Tech stack

| Layer | Choice |
|-------|--------|
| UI | React 18 + TypeScript |
| Build | Vite |
| Styling | Tailwind CSS + custom CSS |
| Icons | lucide-react |
| Maps | OpenStreetMap embed + Nominatim search |

No backend is required for the current MVP. All inputs stay in the browser. Location search uses the public Nominatim API (please use it lightly).

---

## Current scope & limits

**Works today**

- Manual plot details (name, area, access side)
- Location search and “use my location”
- Preference selection
- Three concept options with scores and short rationales
- Editable material rates and indicative cost comparison
- Text export of the selected plan

**Not yet implemented**

- Drawing or uploading real plot corner coordinates
- Live solar / wind calculation (pvlib-style)
- Real geometry optimisation (Shapely / FastAPI pipeline described in the pitch deck)
- 3D preview (Three.js)
- Account or cloud save

The pitch deck describes a full optimisation loop (hard constraints → generate variants → score → explain). The shipped frontend is a usable concept demo that follows that flow with fixed illustrative geometry so a failed phone scan or missing backend cannot break the experience.

---

## Project structure

```
TIMMY-main/
├── index.html
├── package.json
├── vite.config.ts
├── tailwind.config.js
├── src/
│   ├── main.tsx
│   ├── App.tsx          
│   ├── index.css        
│   └── vite-env.d.ts
└── README.md
```

---

## Design notes

- **Honest language** - Avoids overclaiming. Plans are conversation starters.
- **Local-first** - No login; data stays on the device for the session.
- **Mobile-aware** - Sidebar collapses; primary actions remain reachable.
- **Explainable** - Each option includes a short “why this one” note and simple metrics.

---

## Roadmap (suggested)

1. Polygon editor for real plot boundaries and setbacks
2. Lightweight sun-path / exposure heuristic from lat/lon
3. Optional FastAPI service for geometry scoring (Shapely)
4. PDF export with diagram and cost table
5. Offline-capable PWA shell

---

## Licence & responsibility

Prototype for educational and demonstration use at Nirmaan 2026. Not a substitute for professional site analysis, structural design, or statutory approvals. Always have local experts review before building.
