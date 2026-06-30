# St Light — catalog website

This folder is ready to upload to GitHub as-is. It's a plain website (no app store, no build step) — anyone opens it as a link in their browser.

## 1. Put it on GitHub

1. Create a new repository, e.g. `st-light-catalog`. Keep it **public** (required for the free hosting below).
2. Upload everything in this folder to the repo (drag and drop on the GitHub website works fine, or use git).
3. Go to **Settings → Pages**. Under "Build and deployment", set Source to **Deploy from a branch**, branch `main`, folder `/ (root)`. Save.
4. After a minute, GitHub shows your live link, something like:
   `https://yourusername.github.io/st-light-catalog/`

That link is your whole catalog. Share it as-is, or with `?category=solar` / `?category=solar&item=panel-01` added for a specific category or item.

## 2. Add a new product (the only routine task)

1. Open the `images/lighting` or `images/solar` folder in GitHub → **Add file → Upload files** → upload the photo. Square photos look best (the cards crop to a square).
2. Open `catalog.json` (pencil icon to edit) and add a new block inside the right category's `items` list:
   ```json
   {
     "id": "panel-02",
     "name": "300W Solar Panel",
     "image": "images/solar/panel-02.jpg"
   }
   ```
   - `id` must be unique across the whole file — short, no spaces (e.g. `panel-02`).
   - `image` must match the exact filename you uploaded.
3. Commit the change. The live site updates within a minute or two — no other steps needed.

## 3. Add a whole new category

Add a new block to the top-level `categories` list in `catalog.json`:
```json
{
  "id": "fans",
  "name": "Fans",
  "icon": "&#128168;",
  "blurb": "Ceiling and standing fans",
  "items": []
}
```
Then create a matching folder under `images/` (e.g. `images/fans/`) and add items as in step 2.

## 4. Editing or removing a product

- To rename or swap a photo: edit the matching block in `catalog.json`, or upload a new file with the same name (GitHub will ask if you want to replace it).
- To remove a product: delete its block from `catalog.json`. You can leave the photo in the `images` folder or delete it too — doesn't matter, only what's listed in `catalog.json` shows on the site.

## Notes

- Favorites are saved in each visitor's own browser (not shared, no login needed). Clearing browser data clears their favorites.
- Tapping a photo opens a bigger view. Long-pressing a photo (or tapping the heart icon) saves it to favorites.
- Prices are intentionally not shown — just photos and names, per the brief.
