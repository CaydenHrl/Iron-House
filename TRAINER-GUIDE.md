# Iron House — Trainer Card Guide

Everything you need to add, edit, or remove a trainer from the platform.
All changes happen in one place: the `TRAINERS` array at the top of `trainers.html`.

---

## Where to find it

1. Go to your GitHub repo
2. Click `trainers.html`
3. Click the **pencil icon** (Edit this file)
4. Scroll to the top of the `<script>` section — you'll see `const TRAINERS = [`
5. Everything between the `[` and `]` is your trainer roster

---

## Adding a new trainer

Copy the block below, paste it inside the `TRAINERS` array after the last trainer's closing `},` and fill in their details.

```javascript
{
  // ── BASIC INFO ──────────────────────────────────────────────
  name:       "First Last",
  age:        00,
  location:   "City, ST",

  // ── IMAGES ──────────────────────────────────────────────────
  // To use real photos:
  //   1. In GitHub, click "Add file" → "Upload files"
  //   2. Create a folder called "images" if it doesn't exist
  //   3. Upload the photo
  //   4. Replace null with "images/filename.jpg"
  // Leave as null to show the emoji placeholder instead

  img:        null,       // main profile photo
  img2:       null,       // physique or gym photo
  img3:       null,       // lifestyle photo
  emoji:      "💪",      // shows if img is null
  emoji2:     "🏋️",     // shows if img2 is null
  emoji3:     "🥗",      // shows if img3 is null

  // ── RATING ──────────────────────────────────────────────────
  // Set to null and false until they have real reviews
  rating:     5.0,
  reviews:    0,
  founding:   true,       // set to false for non-founding trainers

  // ── CREDENTIALS ─────────────────────────────────────────────
  experience: "X yrs",    // e.g. "4 yrs" or "10+ yrs"
  certs:      "NASM",     // keep short — e.g. "ACE", "ISSA", "BS Kin"
  price:      149,        // number only, no $ sign

  // ── TAGS (show on card) ──────────────────────────────────────
  // specialties: list as many as apply
  specialties: ["Hypertrophy", "Strength"],

  // vibe: pick ONE — this shows as the blue tag on the card
  // Options: "Laid-back", "Encouraging", "High-energy",
  //          "Structured", "Motivating", "No-nonsense"
  vibe:        "Laid-back",

  // diet: pick ONE — this shows as the amber tag on the card
  // Options: "Carnivore", "Plant-based", "Keto", "Whole foods",
  //          "Flexible", "High protein", "Vegan", "Fasting"
  diet:        "High protein",

  // ── INTERESTS (3–5) ─────────────────────────────────────────
  interests:   ["Hiking", "Cooking", "Dogs"],

  // ── COPY ────────────────────────────────────────────────────
  // bio: shows on the card — keep to 2-3 sentences max
  bio:   "Write their short bio here. 2–3 sentences, first person voice.",

  // story: shows when client clicks to open full profile
  story: "Write their full story here. Who they are, why they coach, what they believe in, and what a client can expect working with them.",

  // ── TESTIMONIALS ────────────────────────────────────────────
  // Leave empty [] if none yet — the section won't appear
  // Add as many as you want
  testimonials: [

    // TEXT ONLY (no photos):
    {
      name:     "Client Name",
      initials: "CN",
      result:   "Short result line — e.g. Lost 18 lbs in 10 weeks",
      quote:    "Client's testimonial quote here.",
    },

    // WITH BEFORE/AFTER PHOTOS (client must consent):
    {
      name:     "Client Name",
      initials: "CN",
      result:   "Short result line",
      quote:    "Client's testimonial quote here.",
      before:   "images/clientname-before.jpg",
      after:    "images/clientname-after.jpg",
    },

  ]
},
```

**Make sure there's a comma after the `}` unless it's the very last trainer in the array.**

---

## Editing an existing trainer

Find their block by searching (Ctrl+F / Cmd+F) for their name.
Change whatever field needs updating — price, bio, rating, photos, etc.
Click **Commit changes** when done.

---

## Updating a trainer's rating

Once a trainer gets real reviews, update these two fields:
```javascript
rating:  4.8,    // one decimal place
reviews: 23,     // total number of reviews
```

---

## Adding photos

**Step 1 — Upload to GitHub**
- In your repo, click **Add file → Upload files**
- Upload the photo (JPG or PNG, ideally under 2MB)
- Recommended naming: `firstname-main.jpg`, `firstname-gym.jpg`, `firstname-life.jpg`
- Put all photos in an `images/` folder to keep things tidy

**Step 2 — Update the trainer block**
```javascript
img:   "images/marcus-main.jpg",    // was null
img2:  "images/marcus-gym.jpg",     // was null
img3:  "images/marcus-life.jpg",    // was null
```

**Photo guidelines**
| Slot | What to use | Crop |
|------|-------------|------|
| `img` (main) | Clear headshot or upper body, face visible | Square or portrait |
| `img2` (physique/gym) | Physique shot, lifting, or coaching | Portrait |
| `img3` (lifestyle) | Something personal — outdoors, hobby, dog | Any |

---

## Adding a testimonial with before/after photos

1. Get written consent from the client first
2. Upload both photos to your `images/` folder
   - Recommended naming: `clientfirstname-before.jpg` / `clientfirstname-after.jpg`
3. Add to the trainer's `testimonials` array:

```javascript
{
  name:     "Jamie T.",
  initials: "JT",
  result:   "Lost 22 lbs in 14 weeks",
  quote:    "Their quote here.",
  before:   "images/jamie-before.jpg",
  after:    "images/jamie-after.jpg",
}
```

If the client doesn't want photos shown, just leave out `before` and `after` — it becomes a clean text quote card automatically.

---

## Removing a trainer

Find their block and delete everything from the opening `{` to the closing `},` (including the comma).

---

## Removing the "Founding" badge

Once you move past the founding phase, set a trainer's founding flag to false:
```javascript
founding: false,
```

---

## Quick reference — all fields

| Field | Type | Example | Required? |
|-------|------|---------|-----------|
| `name` | text | `"Marcus Reyes"` | ✅ |
| `age` | number | `29` | ✅ |
| `location` | text | `"Tampa, FL"` | ✅ |
| `img` | path or null | `"images/marcus.jpg"` | ✗ |
| `img2` | path or null | `null` | ✗ |
| `img3` | path or null | `null` | ✗ |
| `emoji` | emoji | `"💪"` | ✅ (fallback) |
| `emoji2` | emoji | `"🏋️"` | ✅ (fallback) |
| `emoji3` | emoji | `"🥗"` | ✅ (fallback) |
| `rating` | decimal | `4.9` | ✅ |
| `reviews` | number | `84` | ✅ |
| `founding` | true/false | `true` | ✅ |
| `experience` | text | `"6 yrs"` | ✅ |
| `certs` | text | `"NASM"` | ✅ |
| `price` | number | `149` | ✅ |
| `specialties` | array | `["Hypertrophy"]` | ✅ |
| `vibe` | text | `"Laid-back"` | ✅ |
| `diet` | text | `"Carnivore"` | ✅ |
| `interests` | array | `["Hiking", "Dogs"]` | ✅ |
| `bio` | text | `"2–3 sentence bio"` | ✅ |
| `story` | text | `"Full story..."` | ✅ |
| `testimonials` | array | `[]` or `[{...}]` | ✅ (can be empty) |

---

## Common mistakes to avoid

- **Missing comma** between trainer blocks — if the page breaks after you add someone, this is almost always why. Every trainer block ends with `},` except the very last one which just ends with `}`
- **Wrong quote type** — always use straight quotes `"like this"` not curly quotes `"like this"`
- **Image path wrong** — make sure the filename and folder name match exactly, including capitalization. `images/Marcus.jpg` and `images/marcus.jpg` are different files.
- **Price as a string** — write `price: 149` not `price: "$149"` — no quotes, no dollar sign

---

*Last updated: 2025 — Iron House internal guide*
