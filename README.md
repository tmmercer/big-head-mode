# Big Head Mode 🤪

Turn your friend's face into a ridiculous looping GIF — right in the browser.

1. Upload a photo and fit their face in the oval (drag, pinch or zoom, tilt, and set the eye line). Tap **💾 Save this face** to keep it on your saved-faces shelf for next time (stored only in your browser, via IndexedDB).
2. Dress them up: 8 hats (top hat, crown, cowboy, propeller, viking, chef, wizard) plus 7 wigs and hairstyles (afro, mohawk, pigtails, mullet, clown wig, sweatband, backwards cap) that show in every animation — on **Auto**, each Full Body animation picks its own look — and 6 outfits (suit, superhero, hot dog, ballerina, Hawaiian, chicken).
3. Pick one of 29 animations: Bobblehead, Deal With It, Spin Cycle, Dramatic Zoom, Disco Bounce, Face Rain, Full Rage, Jelly Wobble, Blast Off, Clone Army, Party Hat, Laser Eyes, Sad Cloud, Pop Art, Peekaboo, Vibe Trail — plus a 🕺 Full Body pack (Dance Floor, Flex, Running Late, Jumping Jacks, The Floss, Power Pose) and a 💼 Strategy Manager pack: Up & To The Right, The Pivot, 2×2 Matrix, Exec Deck, Sticky Notes, Big Idea, Bear Market.
4. Add meme captions, pick a speed, and hit **Make the GIF**. Save or share it.

Everything runs client-side (a tiny built-in GIF encoder, no libraries). Photos never leave the device.

## Run locally

It's a single static file — open `index.html` in a browser, or:

```sh
npx serve .
```

## Deploy

Static site; deploys on Vercel with no build step (framework preset: **Other**).
