# Glow.moe Translations

Translations for glow.moe, split by area of the site:

- `landing/` : the public landing page, nav, footer and help center.
- `dashboard/` : the logged-in dashboard (not translated yet).

Each folder holds one JSON file per language (`tr.json`, `es.json`, ...). The
keys match the app's i18n keys; English is the source/default and lives in the
app code.

## Adding or editing a language
Copy an existing file in the right folder, rename it to the language code, and
translate the values. Keep the keys and any HTML tags inside the values intact.
