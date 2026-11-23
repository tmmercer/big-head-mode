# T$ GIF Creator 🤪

Turn your friend's face into a ridiculous looping GIF — right in the browser.

Two pages: **1 · Pick the face**, then **Next →** to **2 · Make the GIF** (the phone's back button goes back).

1. Upload a photo — the face is found automatically (eyes leveled, zoomed to fit; group photos get a **Next face** button) — and fine-tune it in the oval — or tap **✂️ Trace head** and trace around their head (hair included) with your finger for a custom cutout (🧲 Smart cut-out runs a GrabCut-style graph cut on the device to separate hair and face from the background; fix anything with the ➕ Keep / ➖ Erase brush, with undo; edges are feathered) — or tap **✨ Auto** for an AI cut-out (MediaPipe selfie-multiclass segmenter, loaded from jsDelivr + Google's model host on first use, ~25 MB, runs on the device; keeps hair, face and accessories) (drag, pinch or zoom, tilt, and set the eye line). Tap **💾 Save this face** to keep it on your saved-faces shelf for next time (stored in your browser — or, if you **sign in** with email + password, in your account so they follow you to every device).
   Add a **Friend 2** face (optional) for the 👥 Duo pack, and type each friend's **name** — it shows up in the jokes (chat headers, profile cards, VS screens).
2. Dress them up: 8 hats (top hat, crown, cowboy, propeller, viking, chef, wizard) plus 7 wigs and hairstyles (afro, mohawk, pigtails, mullet, clown wig, sweatband, backwards cap) that show in every animation — on **Auto**, each Full Body animation picks its own look — and 10 outfits (suit, superhero, hot dog, ballerina, Hawaiian, two team jerseys, traveler cloak, grocery apron, chicken).
3. Pick one of 40 animations (packs fold open and closed; 🎲 **Surprise me** picks a random animation and look): Bobblehead, Deal With It, Spin Cycle, Dramatic Zoom, Disco Bounce, Face Rain, Full Rage, Jelly Wobble, Blast Off, Clone Army, Party Hat, Laser Eyes, Sad Cloud, Pop Art, Peekaboo, Vibe Trail, 11:11 Wish, Snack Break, Snack Cake Box (your friend as the brand logo) — plus 🎞️ **Your GIF** (upload any GIF: it's decoded in the browser, the face is tracked in every frame with face-api, and your friend's face is swapped in, matching size, tilt and timing; Switch person for group GIFs; 👥 Two faces puts Friend 1 and Friend 2 on two different people, each tracked separately, with ⇄ Swap; drag-to-place when no face is found; Mouth: 🗣️ Jaw flap moves your friend's jaw with the speaker, 👄 Their lips pastes the speaker's real mouth on), a 📅 Days of the Week pack (Marvelous Monday, Terrific Tuesday, Wonderful Wednesday, Thrilling Thursday, Fortunate Friday, Sensational Saturday, Snoozy Sunday — today's is badged), a 👥 Duo pack (💍 Tailgate Proposal, Face Off, Dance Battle, Slow Dance, Bull vs Bear), a 🕺 Full Body pack (🖼️ **Your Scene** — up to 6 dancers on a background photo you upload — zoom/slide the photo to frame it, then give each dancer their own face, move, outfit, size and spot (drag to place, pinch to resize, drag the ↻ handle or twist to rotate) — plus 🎶 Ocarina Glade, 🥛 Milk Slinger (a grocery worker windmill-hurling gallons in the dairy aisle), 🦛 Hippo Pool (your friend in a Fiona tee waving at a baby hippo who pops up for a big yawn; the Fiona tee is also in Dress them up), Dance Floor, Flex, Running Late, Jumping Jacks, The Floss, Power Pose) and a 💼 Strategy Manager pack: Up & To The Right, The Pivot, 2×2 Matrix, Exec Deck, Sticky Notes, Big Idea, Bear Market, Bull Market — and a 💘 Office Romance pack (Teams DM, Camera On, Open To Love, Connect Request, Calendar Invite, Heart Eyes).
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
