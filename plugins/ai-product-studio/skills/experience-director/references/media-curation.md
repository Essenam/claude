# Media Curation Playbook

## 1. Write a shot list before searching
For each section that needs media, specify: purpose in the narrative, subject, location, shot type (wide establishing / medium / detail / aerial), orientation & aspect ratio, light (golden hour, overcast, interior tungsten…), people (who, doing what, diversity that matches the real audience), and mood.

## 2. Search well
- Use specific queries: place + subject + activity + light ("Nairobi fintech office team meeting daylight", "container port aerial dusk Tema"), not "business people".
- Prefer sources with clear licenses: Unsplash, Pexels, Pixabay (photos/video); Coverr, Mixkit (video); Wikimedia Commons (check each file's license); government/open-data imagery (check terms); the client's own brand assets.
- Pull 3–5 candidates per slot, then pick for **set coherence** over individual beauty.

## 3. Coherence checklist
- [ ] Same geography/cultural context as the product's audience
- [ ] Consistent light temperature and contrast
- [ ] Consistent lens feel (no mixing fisheye drone with shallow-DOF portraits in the same row)
- [ ] People look like real professionals in real environments, not posed stock
- [ ] A single grade applied across the set
- [ ] Each image does a narrative job (establishes place, shows the user, shows the outcome, shows scale)

## 4. Technical treatment
- Responsive `srcset`/`<picture>`, AVIF/WebP, explicit width/height to prevent layout shift, `loading="lazy"` below the fold, `fetchpriority="high"` for the hero.
- Video: `muted autoplay loop playsinline preload="metadata" poster=…`; pause when off-screen; static poster when `prefers-reduced-motion: reduce`; ≤ ~4MB for hero loops.
- Text over media: always a scrim/gradient so contrast passes AA.
- Grade via CSS (`filter`, `mix-blend-mode` overlays) or a pre-processed export so mixed sources match.

## 5. Credits & licensing
Record in `media-credits.md`: file, source URL, author, license, modifications. Never use media with unclear rights in anything that may ship. Do not imitate a real company's brand or pass off people in stock photos as real named customers.

## 6. When media can't be used
Build an art-directed placeholder: correct ratio, gradient/duotone in the brand grade, a subtle texture or map/data motif, and a caption specifying the exact asset to drop in ("Replace with: aerial, dusk, Lagos–Ibadan expressway, trucks moving, 16:9, warm grade"). Never ship an empty grey box.
