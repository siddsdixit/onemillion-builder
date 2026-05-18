# Day 12: Build — Authentication (Sprint S1)

**Time: 20 minutes | Phase: BUILD**

---

## Learn (5 min)

Sprint S1 is always authentication. Every product that has users needs:
- Register (create account)
- Login (get JWT tokens)
- Protected routes (redirect to login if no token)
- Logout (clear tokens)

The BUILD agent uses Argon2 for password hashing (stronger than bcrypt) and JWT for session tokens (15-minute access token, 7-day refresh token). Rate limiting is on auth endpoints (10 requests/minute) to block brute force attacks.

By the end of S1, you can create an account, log in, and see your app as a real user.

## Do (10 min)

1. The BUILD agent should automatically continue to S1 after S0 is verified. If not:
   ```
   Continue to sprint S1
   ```

2. When S1 completes, test the auth flow:
   ```bash
   # Register
   curl -X POST http://localhost:8000/api/v1/auth/register \
     -H "Content-Type: application/json" \
     -d '{"email":"you@example.com","password":"Test1234!","name":"Your Name"}'

   # Login
   curl -X POST http://localhost:8000/api/v1/auth/login \
     -H "Content-Type: application/json" \
     -d '{"email":"you@example.com","password":"Test1234!"}'
   ```

3. Open the frontend at `http://localhost:3000` and register a real account.

4. Try to access a protected route without being logged in — you should be redirected to the auth page.

## Reflect (5 min)

**Assignment:** What does good auth feel like from a user perspective? What's the first thing a new user does after creating an account in your product?

---

**→ Next: [Day 13 — Build: Core Feature](../day-13/learn.md)**
