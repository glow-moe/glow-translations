# glow.moe translations

All the text for glow.moe lives here so it can be translated without touching the
app code. English is the source and stays in the code. Every other language is a
set of JSON files in this repo.

## Layout

Two folders, one per part of the site:

- `landing/` : the public pages (home, footer, help center).
- `dashboard/` : everything you see after logging in.

Inside each, one file per language, named by its code. We currently ship
`tr.json`, `es.json`, `ja.json` and `pt-BR.json`. `en.json` is the English
reference, leave it alone.

A file is just key/value pairs:

```json
{
  "OV_EDIT_LINKS_TITLE": "Edit your links",
  "SB_SHARE": "Share"
}
```

You only change the value on the right. Never touch the key on the left.

## Rules

Get these wrong and the site breaks, so read them once:

**Keep every key.** The key on the left is the ID the app looks up. Renaming or
deleting one breaks that string (it falls back to English at best). Your file
should have the exact same keys as `en.json`, no more, no less.

**Leave `{...}` alone.** Placeholders like `{n}`, `{name}`, `{host}`, `{count}`
get swapped for real values when the page loads. Keep them exactly. You can move
one to a different spot in the sentence, but do not translate or rename it.

- `"{n} clicks"` in German is `"{n} Klicks"`, not `"{Anzahl} Klicks"`.

**Do not touch HTML tags.** A few landing strings have tags like
`<span class="...">`, `<b>`, `<br>`. Translate the words around them, leave the
tags exactly as they are.

**Ampersands, the one fiddly thing:**

- Value has tags in it, write `&amp;`. Example: `"Steam &amp; PSN games..."`.
- Value is plain text with no tags (and everything in `dashboard/`), write a
  normal `&`. Example: `"themes & colors"`.

Simple version: tags in the line means `&amp;`, no tags means `&`. If unsure,
copy whatever the English source does for that key.

**Don't translate names.** Brand and product names stay as-is: Glow, Glow+,
glow.moe, Discord, Steam, PSN, Xbox, MyAnimeList, AniList, Spotify, League,
Valorant, Forza, OBS, and so on. URLs stay too.

**Keep the emoji and faces.** The ✦ ✨ 💖 and little kaomoji like `(๑˃ᴗ˂)` are
part of the vibe. Leave them where they are.

**Write real characters.** Use the proper accented letters for your language
(ç ö ü ş ğ ı, ñ á é í, etc.). Don't flatten them to plain ASCII.

## Tone

glow is casual and cute, made for gamers and anime fans. Keep it short, friendly
and lowercase-leaning, not stiff or corporate. Skim a few existing lines in
`tr.json` or `ja.json` first to catch the feel, then match it.

## Adding a new language

1. Copy `en.json` in both `landing/` and `dashboard/`.
2. Rename each to your language code: `it.json`, `ko.json`, `pl.json`. Only add a
   region (`pt-BR`) when it actually matters.
3. Translate the values, following the rules above.
4. Open a pull request, or just send the two files.

Someone wires it into the app afterwards and it shows up in the language picker.
You never need to open the code.

## Before you submit

- It is still valid JSON (no trailing comma, quotes balanced). Paste it into any
  JSON checker if you are not sure.
- Same keys as `en.json`, nothing missing or added.
- Placeholders and tags untouched.
