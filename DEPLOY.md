# Deploy guide

How to get this from your computer to a live URL. Three paths, all free.

---

## ⏱️ Fastest path — Vercel (recommended, ~5 minutes)

### 1. Push to GitHub

```bash
cd ali-khedr-portfolio

git init
git add .
git commit -m "Initial cinematic portfolio rebuild"
git branch -M main

# Create a new repo on GitHub.com first (any name, public or private), then:
git remote add origin https://github.com/YOUR-USERNAME/ali-khedr-portfolio.git
git push -u origin main
```

### 2. Deploy on Vercel

1. Go to https://vercel.com and sign in with GitHub
2. Click **Add New → Project**
3. Find your repo, click **Import**
4. Leave all settings at defaults (Vercel auto-detects it's a static site)
5. Click **Deploy**

You'll get a live URL like `ali-khedr-portfolio.vercel.app` in under a minute.

### 3. Attach your domain (optional)

If you have or buy a domain (e.g. `alikhedr.com`):
1. Vercel dashboard → your project → **Settings → Domains**
2. Add your domain, follow the DNS instructions
3. SSL certificate is automatic — done.

**Recommended domain registrars**: Namecheap (~$10/year for `.com`), Porkbun (cheaper), Cloudflare (cheapest).

---

## Alternative — GitHub Pages (free, slightly more limited)

If you'd rather keep everything inside GitHub:

1. Push to GitHub (same as Step 1 above)
2. Repo Settings → **Pages**
3. Source: **Deploy from a branch**, branch `main`, folder `/ (root)`
4. Save. Site goes live at `https://YOUR-USERNAME.github.io/ali-khedr-portfolio/`

**Trade-offs vs Vercel**:
- ✅ Free, hosted by GitHub
- ❌ No automatic preview URLs for branches
- ❌ Slower invalidation when you push updates
- ❌ Custom domain setup is more manual

---

## Alternative — Netlify

Functionally identical to Vercel. If you prefer Netlify, the flow is the same: connect GitHub, import repo, deploy.

---

## After it's live

**Test on real devices.** Pull up the live URL on your phone, a tablet, and a laptop. The motion design will reveal any rough edges you can't see in dev.

**Test with throttled connection.** Chrome DevTools → Network tab → throttle to "Fast 3G". The site should still feel responsive — videos take longer to start, but the hero text should still appear cleanly.

**Check Lighthouse scores.** DevTools → Lighthouse → Generate report. Aim for 90+ on Performance, Accessibility, Best Practices, and SEO.

---

## Pushing updates

After the initial deploy, any `git push` automatically redeploys on Vercel/Netlify. So the workflow becomes:

```bash
# Make changes locally, then:
git add .
git commit -m "Describe what changed"
git push

# Site updates within 30-60 seconds.
```

---

## If something breaks

**Images don't load on the live site but work locally:** check that your image paths in `index.html` are relative (`assets/images/...`), not absolute (`/Users/you/Desktop/...`).

**Fonts look wrong:** Google Fonts may be blocked by some CSPs. If you need self-hosted, download the Fraunces variable font and reference it locally in `assets/fonts/`.

**Smooth scroll jittery on mobile:** Lenis already auto-disables on touch devices, but if it's still off, you can conditionally disable it: in the JS, replace `new Lenis({...})` with `window.matchMedia('(pointer:fine)').matches ? new Lenis({...}) : null`.

**YouTube embed not autoplaying:** Browsers require `mute=1` for autoplay. The embed URL already has this — if it still doesn't autoplay, the browser is blocking iframes (some privacy settings do this).
