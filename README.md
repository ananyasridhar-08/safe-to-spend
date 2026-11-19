# Safe-to-Spend · Design Thinking prototype

One clear number: how much Sara can safely spend today. Includes a **simulated read-only bank connection** and security features (2-step sign-in, "Was this you?" alerts, scam check, app lock, revoke access).

Everything is simulated and stored only in your browser. The banks are fictional.
Demo codes appear as pop-up "texts". App-lock PIN: **1234**.

```
safe-to-spend/
├── public/index.html   ← the whole app (HTML + CSS + JS)
├── server.js           ← tiny local server (no installs)
├── package.json        ← `npm start`
└── render.yaml         ← Render settings
```

## 1. Run it on localhost (VS Code)

1. Install [Node.js](https://nodejs.org) (LTS) if you don't have it.
2. In VS Code: **File → Open Folder…** → choose `safe-to-spend`.
3. Open the terminal (**Terminal → New Terminal**) and run:
   ```bash
   npm start
   ```
4. Open **http://localhost:3000**. Stop it with `Ctrl + C`.

No Node? Install the **Live Server** extension, right-click `public/index.html` → **Open with Live Server**.

## 2. Put it on GitHub

Create an empty repo on github.com called `safe-to-spend` (no README), then in the VS Code terminal:

```bash
git init
git add .
git commit -m "Safe-to-Spend prototype"
git branch -M main
git remote add origin https://github.com/YOUR-USERNAME/safe-to-spend.git
git push -u origin main
```

(Or use VS Code's **Source Control** tab → *Publish to GitHub*.)

## 3. Publish on Render (free)

1. Sign in at [render.com](https://render.com) with your GitHub account.
2. **New → Static Site** → pick the `safe-to-spend` repo.
3. Settings:
   - **Build Command:** leave empty
   - **Publish Directory:** `public`
4. Click **Create Static Site**. You get a link like `https://safe-to-spend.onrender.com`.

Every `git push` to `main` redeploys automatically.
(Alternative: **New → Blueprint** uses `render.yaml` with the same settings.)

## Demo script (2 minutes)

1. Log in → enter the code from the pop-up text → set up the budget.
2. Tap **+** to add a cash spend and watch the number change.
3. **Bank** tab → pick a bank → read the permission screen → enter the bank's code.
4. Home shows **Over** because of an unusual AED 349 payment → tap **Not me** → it drops to **Slow down**.
5. **Safety** tab → *Try a scam example* → **Check message**. Turn on App lock.
6. **Recap** tab for the weekly summary.
