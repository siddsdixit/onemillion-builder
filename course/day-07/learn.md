# Day 7: Design Your Product

**Time: 20 minutes | Phase: DESIGN**

---

## Learn (5 min)

The DESIGN agent is a Lead Product Designer. It doesn't use Bootstrap or default component styles — it builds a complete design system using Material Design 3, starting from a single seed color you pick.

One seed color → full palette (primary, secondary, tertiary, error, surface, all dark mode variants). The DESIGN agent queries an M3 MCP server for real component specs, accessibility guidelines, and icon recommendations.

Output includes:
- `design-spec.md` — design direction and decisions
- `design-system.md` — every design token with exact values
- `globals.css` — production CSS ready to copy into the app
- `screens/` — one file per screen with layout specs
- `seed-data.json` — realistic demo data so the app looks alive on first run

## Do (10 min)

1. Continue to design:
   ```
   Continue to design
   ```

2. The agent will ask you for:
   - A **seed color** (one hex code — this generates your entire palette)
   - A **heading font** from Google Fonts

   Pick something that fits your product. A recipe app → warm terracotta. A dev tool → cool slate. A health app → fresh teal.

3. Review the mockup when it's ready:
   ```bash
   cd .onemillion/mockup && python3 -m http.server 8080
   # Open http://localhost:8080
   ```

4. Give feedback:
   ```
   The mockup looks good but I want the cards to be less dense and the color to be darker.
   ```

## Reflect (5 min)

**Assignment:** Screenshot or describe your mockup. What design decision are you most proud of? What did the agent choose that surprised you?

---

**→ Next: [Day 8 — Refine the Design](../day-08/learn.md)**
