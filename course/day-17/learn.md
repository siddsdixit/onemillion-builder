# Day 17: Ship to Production

**Time: 20 minutes | Phase: SHIP**

---

## Learn (5 min)

The SHIP agent follows a 9-phase deployment process. Nothing is "done" until automated curl commands confirm the live URL is working. It deploys backend before frontend, runs smoke tests on the production URL, sets up uptime monitoring, and documents rollback procedures.

By the end of today, you'll have a live URL. Real people can use your product.

You need these accounts before starting (all free tier):
- [MongoDB Atlas](https://mongodb.com/cloud/atlas) — database
- [Railway](https://railway.app) — backend hosting
- [Vercel](https://vercel.com) — frontend hosting
- A GitHub repo with your code pushed

## Do (10 min)

1. Push your code to GitHub:
   ```bash
   git remote add origin https://github.com/your-username/your-product
   git push -u origin main
   ```

2. Run the ship agent:
   ```
   Continue to ship
   ```

3. The agent will walk you through each deployment step. Follow along and confirm each gate passes.

4. When complete, test the live URL:
   ```bash
   curl https://your-app.vercel.app
   # Should return 200

   curl https://your-api.railway.app/api/v1/health
   # → {"status": "ok"}
   ```

5. Share your live URL with one person. Get their first reaction.

## Reflect (5 min)

**Assignment:** Your product is live. Write the URL. Write: "Anyone can now [do X] at [URL]. The first thing I'm going to tell people is [Y]."

---

**→ Next: [Day 18 — Launch](../day-18/learn.md)**
