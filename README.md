# Campus Vendor Marketplace (Web Prototype)

Prototype of the "pay first, offline-first" flow for our PUP vendor marketplace.

## The flow
1. **Browse offline.** The menu, availability, and payment details are saved on the phone.
2. **Pick items and a pickup time.** Each time slot has a limit (5 orders).
3. **Pay in GCash / PayMaya.** The app shows the vendor's QR spot and number (works offline).
4. **Submit the order** with the payment reference number. This is the only step that needs internet.
5. **Pickup.** The student shows the order slip (code like `A-142`) and the receipt. The vendor types the code, checks it, and taps "Hand over". A code that was already used shows a warning.

## Availability
Only **AVAILABLE** / **NOT AVAILABLE**. No stock counts. Vendors switch on what they cooked that morning.

## Try the important cases
- **Offline:** tap the green **Online** badge at the top. Browsing still works, but Submit is disabled.
- **Stale menu:** go offline as a student and add Menudo to the cart. Switch to the Vendor tab, turn Menudo off. Go back online and tap Submit. The app re-checks the live menu, removes Menudo, and warns the student.
- **Used code:** in the Vendor tab, check a code, hand it over, then check the same code again.

## What is fake (on purpose)
- No real login. Student/Vendor tabs are a demo switch.
- Data is stored in `localStorage`, so it only lives on one device. Real syncing needs Firebase (the Android version).
- The QR is a placeholder box.
- Payments are not verified. The vendor still checks the amount and reference number in their own GCash/PayMaya app.
- Scanning is not built. The vendor types the order code.

## Run it
Open `index.html`, or use GitHub Pages (Settings → Pages → deploy from `main`).

Use Github Page: https://egianceazar.github.io/CampusVendorAPP_WebProto/

## Files
- `index.html`: the whole app
- `sw.js`: offline cache
