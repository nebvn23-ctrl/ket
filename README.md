# KET

> In a world full of TEK, we need KET.
> No tech. No AI. No stocks. Just a cat.

Site static (HTML + CSS + JS, animații cu GSAP). Nu are nevoie de build, npm sau server.

## Structura

```
index.html      pagina
config.js       linkul de X și CA (editezi doar aici)
assets/         imagini, video, favicon
.nojekyll       spune GitHub Pages să servească fișierele așa cum sunt
```

## Adaugă X și CA

Deschide `config.js` și completează:

```js
window.KET_CONFIG = {
  X_URL: 'https://x.com/numele_tau',
  CA: 'adresa_contractului'
};
```

Dacă un câmp rămâne gol, site-ul arată „soon” / „coming soon”.
Pe GitHub poți edita direct din browser: deschizi `config.js` → iconița creion → **Commit changes**. Site-ul se actualizează în ~1 minut.

## Publicare pe GitHub Pages

1. Creează un repository nou pe GitHub (de ex. `ket`), public.
2. **Add file → Upload files** și trage în pagină **conținutul** folderului (`index.html`, `config.js`, `assets/`, `.nojekyll`, `README.md`), nu folderul părinte. `index.html` trebuie să fie în rădăcina repo-ului.
3. **Commit changes**.
4. **Settings → Pages → Build and deployment**: Source = *Deploy from a branch*, Branch = `main`, folder `/ (root)` → **Save**.
5. După 1–2 minute site-ul e live la `https://NUMELE-TAU.github.io/ket/`.

> `.nojekyll` începe cu punct și poate fi ascuns în Finder/Explorer. Site-ul funcționează și fără el.

## Domeniu propriu (opțional)

**Settings → Pages → Custom domain**, scrii domeniul (ex. `ketcat.xyz`) și urmezi instrucțiunile DNS afișate de GitHub. Bifează **Enforce HTTPS**.

## Preview pe X / Telegram

În `index.html`, rândul cu `og:image` are o cale relativă. Pentru carduri de preview sigure pune adresa completă după ce site-ul e live:

```html
<meta property="og:image" content="https://NUMELE-TAU.github.io/ket/assets/og.jpg">
```

## Test local

Deschide `index.html` direct în browser, sau rulează în folder:

```
python3 -m http.server 8000
```

și intră pe `http://localhost:8000`.
