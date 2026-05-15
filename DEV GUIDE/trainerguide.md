# Iron House — Trainer Management Guide

---

## When a trainer applies

When a trainer submits their application through the website you'll receive an email from Formspree with all of their answers.

**Review the application and decide if they're a good fit.**

If yes:
1. Send them the orientation email (ask Cayden for the template)
2. Add them to the website using the Trainer Card Generator (https://caydenhrl.github.io/kao1nx9ab82/)
3. Wait for their shirt size and address to arrive by reply, then order their shirt

If no:
1. Send a polite decline — thank them for their time and wish them well

---

## Adding a new trainer to the website

1. Open the **Trainer Card Generator** (ask Cayden for the link)
2. Fill out every section using the information from their application
3. Set their stat sliders — use their questionnaire slider answers directly
4. Click **Add to website**
5. The trainer appears on the site within 60 seconds

That's it. No copying, no pasting, no JSON editing.

---

## Editing an existing trainer

For small changes (rating, price, a typo in their bio):

1. Go to GitHub → open **trainers.json** → click the pencil icon to edit
2. Use Ctrl+F / Cmd+F to search for their name
3. Change only the field you need
4. Click **Commit changes**

For bigger updates (new photos, new bio, new testimonials):
Use the same steps above — find their block and update the relevant fields directly.

---

## Adding photos

Photos must be uploaded to GitHub before they show on the site.

1. Go to the Iron House GitHub repo
2. Click **Add file → Upload files**
3. Drag the photo in — rename it following the naming rules below before uploading
4. Click **Commit changes**
5. Go into trainers.json, find the trainer, update their photo field to match

**Naming rules — always lowercase, always dashes, never spaces:**

| Photo | Name it |
|-------|---------|
| Main profile | `firstname-main.jpg` |
| Gym / physique | `firstname-gym.jpg` |
| Lifestyle | `firstname-life.jpg` |
| Client before | `clientname-before.jpg` |
| Client after | `clientname-after.jpg` |

**Photo specs:**
- All three card slots: portrait crop, ideally 900×1200px (3:4 ratio)
- Before/after testimonial photos: square crop (1:1)
- Keep all photos under 300KB — use squoosh.app to compress if needed

⚠️ Filename in trainers.json must match exactly what you uploaded — capital letters matter.

---

## Updating a trainer's rating

Find their block in trainers.json and update:
```
"rating": 4.8,
"reviews": 23,
```

---

## Adding a testimonial to an existing trainer

Find their block in trainers.json and look for their `"testimonials"` section.

**Text only (no photos):**
```json
{
  "name":    "Jamie T.",
  "initials":"JT",
  "result":  "Lost 22 lbs in 14 weeks",
  "quote":   "Their quote here.",
  "before":  "",
  "after":   ""
}
```

**With before/after photos — only add with client's explicit permission:**
```json
{
  "name":    "Jamie T.",
  "initials":"JT",
  "result":  "Lost 22 lbs in 14 weeks",
  "quote":   "Their quote here.",
  "before":  "images/jamie-before.jpg",
  "after":   "images/jamie-after.jpg"
}
```

If there are already testimonials in their list, add a comma after the last `}` then paste the new block before the closing `]`.

---

## Removing a trainer

1. Open trainers.json → click pencil to edit
2. Find their block — everything from their `{` to their `},`
3. Delete that entire section including the comma
4. Commit changes

---

## New trainer onboarding checklist

- [ ] Application reviewed
- [ ] Orientation email sent
- [ ] Shirt size and address received
- [ ] Shirt ordered
- [ ] Profile added to website via generator
- [ ] Photos uploaded to images/ folder
- [ ] Profile reviewed on live site — looks correct

---

## If something looks broken on the website

The most common cause is a missing or extra comma in trainers.json.

Open the file and look for:
- A `}` without a comma before the next trainer
- An extra comma after the very last trainer
- A missing quote around a text value

If you can't find it, copy the entire file contents and paste it into Claude — it'll spot the problem instantly.

---

*Iron House internal guide*
