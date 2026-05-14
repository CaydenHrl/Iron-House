# Iron House — How to Add & Edit Trainers

All trainer information lives in one file: **trainers.json**

You never need to touch trainers.html. Just edit trainers.json and the website updates automatically.

---

## How to open and edit trainers.json

1. Go to the Iron House GitHub repo
2. Click the file called **trainers.json**
3. Click the **pencil icon** (top right of the file) to edit
4. Make your changes
5. Scroll to the bottom and click **Commit changes**
6. The website will update within about 60 seconds

---

## What trainers.json looks like

The file is a list of trainers. Each trainer starts with a `{` and ends with a `},`

Everything between those curly brackets is that trainer's information.

Here is every field explained in plain English:

---

```
"name"        → Their full name. Example: "Sarah Johnson"

"age"         → Their age as a number. Example: 31

"location"    → Their city and state. Example: "Austin, TX"

"email"       → Their email address. This is for your records only,
                 it does not show on the website.

"price"       → Their monthly rate as a number, no dollar sign.
                 Example: 149

"experience"  → How long they've been coaching.
                 Example: "4 yrs"  or  "10+ yrs"

"certs"       → Their certifications. Keep it short.
                 Example: "NASM"  or  "ACE + BS"

"rating"      → Their star rating. Use one decimal place.
                 Example: 4.8
                 Set to 5.0 when they're new and have no reviews yet.

"reviews"     → How many reviews they have. Just a number.
                 Example: 47
                 Set to 0 when they're new.

"founding"    → Whether they are a founding trainer.
                 Type  true  for yes,  false  for no.
                 (No quotes around true or false)
```

---

```
"photo_main"      → Their main profile photo.
                     How to add a photo — see the Photos section below.
                     Example: "images/sarah-main.jpg"
                     Leave as  ""  (empty quotes) if no photo yet.

"photo_physique"  → A gym or physique photo.
                     Example: "images/sarah-gym.jpg"
                     Leave as  ""  if no photo yet.

"photo_lifestyle" → A lifestyle photo — outdoors, hobby, pet, etc.
                     Example: "images/sarah-life.jpg"
                     Leave as  ""  if no photo yet.
```

---

```
"specialties" → What they specialize in. List as many as apply.
                 Must use square brackets and quotes.
                 Example: ["Hypertrophy", "Strength"]
                 Example: ["Weight Loss", "Cardio & Endurance", "Calisthenics"]

                 Options to choose from:
                 Hypertrophy, Strength, Calisthenics, CrossFit,
                 Weight Loss, Cardio & Endurance, Functional Fitness,
                 Flexibility & Mobility, Sport-Specific, Body Recomposition

"vibe"        → Their coaching personality. Pick ONE.
                 Example: "Laid-back"

                 Options to choose from:
                 Laid-back, Encouraging, High-energy,
                 Structured, Motivating, No-nonsense

"diet"        → Diet approach they coach. Pick ONE.
                 Example: "High protein"

                 Options to choose from:
                 Carnivore, Plant-based, Keto, Whole foods,
                 Flexible, High protein, Vegan, Fasting
```

---

```
"interests"   → 3 to 5 things they enjoy outside the gym.
                 Example: ["Hiking", "Cooking", "Dogs", "Travel"]

"bio"         → Short description that shows on their card.
                 Keep to 2-3 sentences. Write in first person.
                 Example: "I coach people who want real results..."

"story"       → Longer description shown when someone clicks their profile.
                 Can be a full paragraph or two. Write in first person.
```

---

## Testimonials

Each trainer has a testimonials section at the bottom of their block.
You can have as many as you want, or none at all.

**Text only (no photos):**
```
{
  "name":    "Jamie T.",
  "initials":"JT",
  "result":  "Lost 22 lbs in 14 weeks",
  "quote":   "Write the client's quote here.",
  "before":  "",
  "after":   ""
}
```

**With before/after photos (client must give permission first):**
```
{
  "name":    "Jamie T.",
  "initials":"initials":"JT",
  "result":  "Lost 22 lbs in 14 weeks",
  "quote":   "Write the client's quote here.",
  "before":  "images/jamie-before.jpg",
  "after":   "images/jamie-after.jpg"
}
```

Leave `"before"` and `"after"` as empty quotes `""` if there are no photos.
The website will automatically show a clean text card instead — it won't look broken.

If there are no testimonials at all, leave the section as:
```
"testimonials": []
```

---

## How to add photos

**Step 1 — Upload the photo to GitHub**

1. Go to the GitHub repo
2. Click **Add file** → **Upload files**
3. Drag the photo in (JPG or PNG, try to keep under 2MB)
4. In the box that says "Commit changes", just click the green button
5. The photo is now on the website at the path `images/filename.jpg`

**Tip — name photos clearly so they're easy to find:**

| Photo type | Suggested name |
|------------|----------------|
| Main profile | `firstname-main.jpg` |
| Gym / physique | `firstname-gym.jpg` |
| Lifestyle | `firstname-life.jpg` |
| Client before | `clientfirstname-before.jpg` |
| Client after | `clientfirstname-after.jpg` |

**Step 2 — Add the path to trainers.json**

Once uploaded, go back to trainers.json and fill in the photo field:
```
"photo_main": "images/sarah-main.jpg"
```

⚠️ The filename must match exactly — including capital letters.
`images/Sarah-Main.jpg` and `images/sarah-main.jpg` are different.

---

## How to add a new trainer

1. Open trainers.json and click the pencil to edit
2. Scroll to the very end of the last trainer's block — find the last `}` followed by a `]`
3. After that last `}` add a comma, then paste the template below
4. Fill in all the fields
5. Commit changes

**New trainer template — copy and paste this:**
```json
  ,
  {
    "name": "",
    "age": 0,
    "location": "",
    "email": "",
    "price": 0,
    "experience": "",
    "certs": "",
    "rating": 5.0,
    "reviews": 0,
    "founding": true,

    "photo_main": "",
    "photo_physique": "",
    "photo_lifestyle": "",

    "specialties": [],
    "vibe": "",
    "diet": "",
    "interests": [],

    "bio": "",
    "story": "",

    "testimonials": []
  }
```

---

## How to remove a trainer

1. Open trainers.json and click the pencil to edit
2. Find their block — everything from their `{` to their `},`
3. Delete that entire section including the comma
4. Commit changes

---

## Quick reference — photo tips

| Slot | What works best |
|------|----------------|
| Main profile | Clear face visible, good lighting, confident pose |
| Physique / gym | Showing their build, lifting, or coaching someone |
| Lifestyle | Outdoors, with a pet, doing a hobby — something personal |
| Client before/after | Side by side works best, consistent lighting if possible |

---

## Things to double-check before saving

- Every field has quotes around text values: `"like this"`
- Numbers don't have quotes: `149` not `"149"`
- Lists use square brackets: `["Item 1", "Item 2"]`
- true and false have no quotes: `true` not `"true"`
- Every trainer except the last one ends with `},` (with a comma)
- The very last trainer ends with just `}` (no comma)
- Photo filenames match exactly what you uploaded

---

## If something looks wrong on the website

The most common cause is a missing or extra comma somewhere.
Open trainers.json and look for any of these:

- A `}` without a comma before the next trainer
- An extra comma after the very last trainer
- A missing quote around a text value

If you can't find it, just come back to Claude and paste the file — it can spot the problem in seconds.

---

*Iron House — internal guide*
