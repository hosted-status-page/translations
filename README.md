# StatusPage.me - Community Translations

This repository contains **community-maintained translation files** for the StatusPage.me dashboard and user-facing interface.

If you are helping translate the product into your language: thank you.  
If you are here by accident: welcome to the least exciting but most useful part of the app.

---

## What is StatusPage.me?

[StatusPage.me](https://statuspage.me) is a **privacy-first status page and uptime monitoring platform**.

It helps teams communicate outages, incidents, and maintenance clearly and reliably, without relying on third-party trackers, external CDNs, or questionable data flows.

This repository exists **only** for translations.  
No backend code. No UI logic. Just strings.

---

## Repository Structure

```
translations/
├── en.json          # English (source language)
├── es.json          # Spanish
├── pt-br.json       # Portuguese (Brazil)
├── de.json          # German
├── fr.json          # French
├── sr.json          # Serbian (Cyrillic)
└── ar.json          # Arabic
```

- `en.json` is the **source of truth**
- All other files must match its structure exactly

---

## File Naming Logic

Translation files are named after **locale codes** using a simplified **BCP 47** style.

### Rules

- **Lowercase filenames**: use lowercase for consistency across filesystems and tooling.
- **One file per locale**: each file represents a specific language (and optionally region/script).
- **Hyphen-separated subtags**: use `language[-script][-region]` (when needed).
- **JSON extension**: always `.json`.

### Examples

- `en.json` → English (default/source)
- `de.json` → German
- `fr.json` → French
- `pt-br.json` → Portuguese as used in Brazil (language `pt` + region `BR`)
- `sr.json` → Serbian (this repo uses **Cyrillic** for Serbian by convention)
- If we add Serbian Latin in the future: `sr-latn.json` (language `sr` + script `Latn`)
- If we add a region-specific variant: `en-gb.json` (English as used in Great Britain)

### When to add region/script?

Only add region/script when it meaningfully changes the language in the UI:
- Portuguese: `pt-br` vs `pt-pt`
- Chinese: `zh-hans` vs `zh-hant`
- Serbian: `sr` (Cyrillic) vs `sr-latn` (Latin)

If a locale-specific file does not exist, the app should fall back to a more general locale (and ultimately to `en`).

---

## Supported Languages

| Language            | Code    | Status    |
| ------------------- | ------- | --------- |
| English             | `en`    | Source    |
| Spanish             | `es`    | Community |
| Portuguese (Brazil) | `pt-br` | Community |
| German              | `de`    | Community |
| French              | `fr`    | Community |
| Serbian (Cyrillic)  | `sr`    | Community |
| Arabic              | `ar`    | Community |

Improvements are always welcome. Perfection is a myth.

---

## Translation File Format

Each translation file is a JSON object using **nested keys** grouped by feature or page.

Example:

```json
{
  "notification_channels": {
    "heading": "Notification Channels",
    "types": {
      "slack": "Slack",
      "telegram": "Telegram",
      "email": "Email"
    }
  }
}
```

### Key Rules

- **Do not rename keys**
- **Do not remove keys**
- **Do not flatten structures**
- If a key exists in `en.json`, it must exist everywhere

---

## Placeholders & HTML

Some strings include placeholders or HTML. These must be preserved exactly.

### Placeholders

```json
"deleted_items": "You deleted {{count}} items"
```

Do not translate or modify `{{count}}`.

### HTML

```json
"learn_more": "Read more in our <a href='/docs'>documentation</a>"
```

Keep tags intact. Translate only the text.

---

## Brand Names & URLs

- **Do not translate brand names**  
  Slack, Telegram, GitHub, Discord stay as-is.
- **Do not translate URLs or paths**
- **Do not translate code examples**

Yes, even if it looks wrong in your language. It is not wrong.

---

## Language-Specific Notes

### Spanish (`es.json`)
- Use formal “usted”
- Neutral, international Spanish preferred

### Portuguese (`pt-br.json`)
- Brazilian Portuguese only
- Avoid European forms

<small><i>💡 Want to add 🇵🇹 Portuguese (pt-pt)? <a href="https://github.com/hosted-status-page/translations/issues/new">Open an issue first</a></i>.</small>

### German (`de.json`)
- Use formal “Sie”
- Capitalize nouns correctly

### French (`fr.json`)
- Use formal “vous”
- Avoid unnecessary English borrowings

### Serbian (`sr.json`)
- Cyrillic only
- Formal tone
- Proper case usage matters more than literal translation

### Arabic (`ar.json`)
- Modern Standard Arabic
- RTL handling is done by the app

---

## How to Contribute

### Improving Existing Translations

1. Find the key in `en.json`
2. Update the same key in your language file
3. Keep structure unchanged
4. Open a pull request explaining what you fixed

### Adding a New Language

1. Open an issue first
2. Copy `en.json`
3. Translate **all keys**
4. Submit a PR

Partial translations are not accepted. Half-finished languages help no one.

---

## Common Problems

### App shows English instead of your translation
- The key is missing or mismatched
- JSON is invalid
- The key was added recently and not translated yet

### App breaks after your change
- You broke JSON syntax
- You removed a placeholder
- You modified HTML

All fixable. None mysterious.

---

## Sync With Main Repository

Approved translations are periodically synced into the main StatusPage.me codebase and released with regular deployments.

This repo is intentionally simple. No automation, no magic.

---

## License

Translations follow the same license as the main StatusPage.me project.  
See the root `LICENSE` file.

---

## Final Note

Translation work is invisible when done right and very visible when done wrong.

Thanks for doing it right. 🥰

