# RADIX — Sito vetrina

Sito statico (HTML/CSS/JS puro, nessuna build necessaria) per RADIX — Venture & Innovation Studio.
Dominio di destinazione: **radixinnovationstudio.com** (Namecheap).

## Cosa c'è dentro

- `index.html` — l'intera pagina (one-page site: hero, approccio, per chi lavoriamo, competenze, metodo, progetti, brand moment, contatti, footer)
- `assets/` — le immagini usate nel sito (logo, foto/mockup della sezione hero e approccio, sfondo del "brand moment", watermark contatti)

Il modulo di contatto in fondo alla pagina non invia dati a nessun server: apre il client email dell'utente con oggetto e corpo già compilati (`mailto:`), quindi non serve alcun backend per farlo funzionare.

## Come metterlo online (Vercel + dominio Namecheap)

1. **Crea un repository GitHub** (es. `radix-site`), pubblico o privato — indifferente per Vercel.
2. Carica il contenuto di questa cartella nel repository (via `git push` dal tuo Mac, oppure trascinando i file dall'interfaccia web di GitHub — con un sito così semplice funziona bene anche l'upload da browser).
3. Vai su **vercel.com** → **Add New → Project** → **Import** il repository appena creato.
   - Framework preset: lascialo su "Other" (nessun framework, nessun build command: è HTML statico).
   - Build command / Output directory: lasciali vuoti — Vercel serve direttamente `index.html`.
4. Clicca **Deploy**: in circa 30 secondi hai un URL tipo `radix-site.vercel.app` per verificare che sia tutto a posto.
5. Nel progetto Vercel, vai su **Settings → Domains** → aggiungi `radixinnovationstudio.com` (e se vuoi anche `www.radixinnovationstudio.com`).
6. Vercel ti mostra 1-2 record DNS da aggiungere (in genere un record **A** che punta a `76.76.21.21` per il dominio nudo, e un **CNAME** che punta a `cname.vercel-dns.com` per `www`). Vai su **Namecheap → Domain List → Manage → Advanced DNS** e aggiungi esattamente quei record (i valori esatti li conferma Vercel al momento, possono cambiare leggermente).
7. La propagazione DNS richiede da pochi minuti a un paio d'ore; Vercel segnala in automatico quando il dominio è verificato e attiva l'HTTPS da solo.

## Cosa manca / da rivedere con calma (non bloccante per andare online)

- Le immagini in `assets/` sono quelle usate nella bozza di design (mockup/placeholder a bassa risoluzione, in particolare `brand-moment-bg.png` e `hero-portrait.png`): funzionano per andare online subito, ma vale la pena sostituirle con foto/render definitivi in alta risoluzione quando ci sarà materiale vero.
- Testi e struttura ricalcano fedelmente la bozza approvata (canvas "RADIX — Sito Vetrina"); qualunque modifica di copy si fa direttamente in `index.html` (è tutto in italiano semplice, senza framework, facile da modificare anche a mano).
