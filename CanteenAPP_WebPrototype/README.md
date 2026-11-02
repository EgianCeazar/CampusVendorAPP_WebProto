# Campus Vendor Marketplace (Prototype)

A simple prototype for our PUP vendor marketplace project. It shows the core idea:
**light, works with bad internet, and doesn't make vendors do extra work.**

## What it does
- **Vendor daily menu**: vendors turn items on/off ("available" / "sold out"). No stock counts.
- **Browse vendors**: search by vendor or food, filter by category, see stall, hours, and "menu updated" time.
- **Order slip**: student picks items, app computes the total, shows GCash number / QR spot, and makes a slip with a short code (like `A-142`).
- **Pickup slots with a cap**: max 5 orders per 15-minute slot so the queue doesn't just move.
- **Vendor incoming orders**: simple list with one "Mark done" button. No pending/accepted/ready statuses.
- **Offline-friendly**: data is saved on the phone and a service worker caches the app. The badge shows online/offline.

## Run it
Just open `index.html` in a browser. To test the offline caching, use a local server:

```
python -m http.server 8000
```

Then open `http://localhost:8000`. Or turn on **GitHub Pages** (Settings → Pages → deploy from `main`) to open it on a phone.

## What is fake (on purpose)
- No real login. The Student/Vendor tabs are a demo switch.
- Data is stored in `localStorage`, so orders only show up on the same device. Vendor and student sharing orders needs a real backend.
- The QR is a placeholder box.
- Admin approval is not built. In the real app, do it in the Firebase console.

## Next steps
1. Build the Android version (Kotlin or Flutter) with **Firebase Firestore** (has offline cache built in).
2. Add real login with a PUP email.
3. Sync orders to the vendor when there's signal.
4. Replace the QR placeholder with an image the vendor uploads.

## Files
- `index.html`: the whole app (HTML, CSS, JS)
- `sw.js`: offline cache
