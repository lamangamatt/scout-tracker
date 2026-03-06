# Domain & Hosting Options for Scout Tracker

## Free Hosting Options

### 1. GitHub Pages (Recommended) ⭐

**URL**: `https://username.github.io/scout-tracker/`

**Setup**:
1. Push code to GitHub
2. Go to repo Settings → Pages
3. Set Source to `main` branch
4. Your site is live in ~1 minute

**Pros**: Free, reliable, automatic HTTPS, deploys on push
**Cons**: No subdomain customization without custom domain

### 2. Netlify

**URL**: `https://your-site-name.netlify.app`

**Setup**:
1. Sign up at netlify.com
2. Connect your GitHub repo
3. It auto-deploys on push

**Pros**: Custom subdomain names, deploy previews, form handling
**Cons**: Build minutes limited on free tier (plenty for static sites)

### 3. Vercel

**URL**: `https://your-site.vercel.app`

**Setup**: Similar to Netlify, connect GitHub repo

**Pros**: Fast, great developer experience
**Cons**: Mainly designed for Next.js/React apps

### 4. Firebase Hosting

**URL**: `https://your-project.web.app` or `https://your-project.firebaseapp.com`

**Setup**:
```bash
npm install -g firebase-tools
firebase login
firebase init hosting
firebase deploy
```

**Pros**: Integrates with Firebase Database, CDN included
**Cons**: Requires CLI setup

### 5. Cloudflare Pages

**URL**: `https://your-site.pages.dev`

**Pros**: Unlimited bandwidth, fast global CDN
**Cons**: Slight learning curve

---

## Custom Domain Options (Paid)

### Where to Buy Domains

| Registrar | Price/Year | Notes |
|-----------|------------|-------|
| **Namecheap** | $8-12 | Great value, free WHOIS privacy |
| **Google Domains** | $12 | Simple interface (now Squarespace) |
| **Cloudflare** | $8-10 | At-cost pricing, no markup |
| **Porkbun** | $8-10 | Good prices, quirky |

### Good Domain Ideas for Scout Tracker

- `scouttracker.app` (~$15/year)
- `pitchtracker.io` (~$40/year)
- `yourteamname-baseball.com` (~$10/year)
- `binghambaseball.com` (if available)

### Setting Up Custom Domain with GitHub Pages

1. **Buy domain** from registrar of choice

2. **Add DNS records** at your registrar:
   ```
   Type: A
   Name: @
   Value: 185.199.108.153
   
   Type: A
   Name: @
   Value: 185.199.109.153
   
   Type: A
   Name: @
   Value: 185.199.110.153
   
   Type: A
   Name: @
   Value: 185.199.111.153
   
   Type: CNAME
   Name: www
   Value: username.github.io
   ```

3. **Configure in GitHub**:
   - Go to repo Settings → Pages
   - Enter your custom domain
   - Check "Enforce HTTPS" (may take 24h to enable)

4. **Add CNAME file** to repo:
   ```
   yourdomain.com
   ```

---

## Recommendation for Matt

**Start with GitHub Pages** - it's free, you're already using GitHub, and it "just works".

**URL will be**: `https://lamangamatt.github.io/scout-tracker/`

If you want a cleaner URL later:
1. Buy a domain (~$10/year)
2. Point it to GitHub Pages
3. Share something like `scouttracker.app` or `binghambaseball.app`

For now, the GitHub Pages URL works great and you can always add a custom domain later without changing anything else!

---

## Quick Reference

### Current Setup
- **Repo**: `github.com/lamangamatt/scout-tracker`
- **GitHub Pages**: Enable in Settings → Pages
- **Live URL**: `https://lamangamatt.github.io/scout-tracker/`

### Entry Points
- Game Entry: `/entry.html`
- Coach View: `/coach.html`  
- Bullpen: `/bullpen.html`

### Sharing Links
```
Game Entry: https://lamangamatt.github.io/scout-tracker/entry.html
Coach View: https://lamangamatt.github.io/scout-tracker/coach.html
Bullpen:    https://lamangamatt.github.io/scout-tracker/bullpen.html
```
