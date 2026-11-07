# T$ GIF Creator 🤪

Turn your friend's face into a ridiculous looping GIF — right in the browser.

Two pages: **1 · Pick the face**, then **Next →** to **2 · Make the GIF** (the phone's back button goes back).

1. Upload a photo — the face is found automatically (eyes leveled, zoomed to fit; group photos get a **Next face** button) — and fine-tune it in the oval (drag, pinch or zoom, tilt, and set the eye line). Tap **💾 Save this face** to keep it on your saved-faces shelf for next time (stored in your browser — or, if you **sign in** with email + password, in your account so they follow you to every device).
   Add a **Friend 2** face (optional) for the 👥 Duo pack, and type each friend's **name** — it shows up in the jokes (chat headers, profile cards, VS screens).
2. Dress them up: 8 hats (top hat, crown, cowboy, propeller, viking, chef, wizard) plus 7 wigs and hairstyles (afro, mohawk, pigtails, mullet, clown wig, sweatband, backwards cap) that show in every animation — on **Auto**, each Full Body animation picks its own look — and 7 outfits (suit, superhero, hot dog, ballerina, Hawaiian, grocery apron, chicken).
3. Pick one of 40 animations (packs fold open and closed; 🎲 **Surprise me** picks a random animation and look): Bobblehead, Deal With It, Spin Cycle, Dramatic Zoom, Disco Bounce, Face Rain, Full Rage, Jelly Wobble, Blast Off, Clone Army, Party Hat, Laser Eyes, Sad Cloud, Pop Art, Peekaboo, Vibe Trail — plus a 👥 Duo pack (Face Off, Dance Battle, Slow Dance, Bull vs Bear), a 🕺 Full Body pack (🖼️ **Your Scene** — up to 6 dancers on a background photo you upload — zoom/slide the photo to frame it, then give each dancer their own face, move, outfit, size and spot (drag to place, pinch to resize) — plus 🥛 Milk Slinger (a grocery worker windmill-hurling gallons in the dairy aisle), Dance Floor, Flex, Running Late, Jumping Jacks, The Floss, Power Pose) and a 💼 Strategy Manager pack: Up & To The Right, The Pivot, 2×2 Matrix, Exec Deck, Sticky Notes, Big Idea, Bear Market, Bull Market — and a 💘 Office Romance pack (Teams DM, Camera On, Open To Love, Connect Request, Calendar Invite, Heart Eyes).
4. Add meme captions, pick a speed, and hit **Make the GIF**. Save or share it.

Everything runs client-side: a tiny built-in GIF encoder, plus [@vladmandic/face-api](https://github.com/vladmandic/face-api) (MIT, bundled in `vendor/`) for face detection, loaded only when you upload a photo. Photos never leave the device.

## Run locally

It's a single static file — open `index.html` in a browser, or:

```sh
npx serve .
```

## Deploy

Static site; deploys on Vercel with no build step (framework preset: **Other**).

## Accounts (optional)

Sign-in uses Supabase Auth (email + password) via plain REST calls — no SDK. Saved faces for signed-in users live in the `public.tgif_faces` table, protected by row-level security so each account only sees its own faces. The publishable key in `index.html` is meant to be public.

After deploying, add your site URL in Supabase → Authentication → URL Configuration (Site URL and Redirect URLs) so confirmation and password-reset emails link back to the site.
