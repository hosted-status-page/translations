# Status Page Dashboard - Community Translations

👋🏻 Welcome! 

This repository contains translation files for the Status Page Dashboard application. 

We appreciate community contributions to improve and expand language support. 🥰

## 📁 Repository Structure

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

## 🌐 Supported Languages

| Language            | Code    | Status     | Help Needed          |
| ------------------- | ------- | ---------- | -------------------- |
| English             | `en`    | ✅ Complete | Reference language   |
| Spanish             | `es`    | ✅ Complete | Improvements welcome |
| Portuguese (Brazil) | `pt-br` | ✅ Complete | Improvements welcome |
| German              | `de`    | ✅ Complete | Improvements welcome |
| French              | `fr`    | ✅ Complete | Improvements welcome |
| Serbian             | `sr`    | ✅ Complete | Improvements welcome |
| Arabic              | `ar`    | ✅ Complete | Improvements welcome |

**Want to add a new language?** Please open an issue first to coordinate with the team.

## 📖 File Structure

Each translation file is a JSON object with a hierarchical structure. Keys are organized by feature/page:

```json
{
  "notification_channels": {
    "heading": "Notification Channels",
    "subtitle": "Configure notification channels...",
    "types": {
      "slack": "Slack",
      "telegram": "Telegram",
      "email": "Email"
    }
  },
  "status_pages": {
    "heading": "Status Pages",
    "form": {
      "name_label": "Status Page Name",
      "slug": "URL Slug"
    }
  }
}
```

### Key Naming Conventions

- **Dot notation for nesting**: `notification_channels.types.slack` refers to the nested value
- **Descriptive names**: Keys describe their purpose (e.g., `help`, `label`, `placeholder`, `error`)
- **Consistency**: Similar UI elements use consistent key names across the app

## 🚀 How to Contribute

### For Fixing/Improving Translations

1. **Find the key** you want to improve by searching `en.json`
2. **Edit the corresponding key** in your language file (e.g., `es.json`)
3. **Test your changes** (see section below)
4. **Submit a pull request** with a clear description of what you improved

### For New Languages

1. **Open an issue** to request a new language
2. **Copy `en.json`** as a template for your new language file
3. **Translate all keys** following the guidelines below
4. **Submit a pull request** and we'll review it together

## ✅ Translation Guidelines

### General Rules

- **Keep HTML tags**: Some strings contain HTML (like `<a>`, `<strong>`). Preserve them exactly.
  ```json
  ❌ "Learn more at our site" (removed the link)
  ✅ "Learn more at our <a href='/docs'>site</a>" (preserved HTML)
  ```

- **Preserve placeholders**: Strings with `{{variable}}` must keep them for dynamic content.
  ```json
  ❌ "You have deleted 5 status pages"
  ✅ "You have deleted {{count}} status pages"
  ```

- **Keep special characters**: Emojis, arrows, and symbols should be preserved unless context requires otherwise.
  ```json
  ✅ "✓ Current" (the checkmark is intentional)
  ✅ "→ Next" (the arrow is intentional)
  ```

- **Brand names**: Keep brand names unchanged (Slack, Telegram, Discord, etc.)
  ```json
  ✅ "Slack Configuration"
  ❌ "Configuración Holgura" (don't translate brand names)
  ```

- **URLs and email addresses**: Never translate URLs or email example addresses.
  ```json
  ✅ "https://discord.com/api/webhooks/..."
  ❌ "https://discord.com/api/ganchos/..." (don't translate path parts)
  ```

### Language-Specific Guidelines

#### Spanish (es.json)
- Use formal "usted" form for user-facing messages
- Currency: Keep as USD unless specified otherwise
- Date format: DD/MM/YYYY

#### Portuguese (pt-br.json)
- Use Brazilian Portuguese conventions
- Common abbreviations: "ex." for example, "obs." for observation
- Currency: Use "R$" for Brazilian Real when appropriate

#### German (de.json)
- Capitalize nouns (German convention)
- Use formal "Sie" for user-facing messages
- Gender-neutral forms where possible

#### French (fr.json)
- Use formal "vous" for user-facing messages
- Avoid anglicisms when French equivalents exist
- Respect French capitalization rules (minimal caps)

#### Serbian (sr.json)
- Use Cyrillic script (already in file)
- Formal "Ви" form for user-facing messages
- Respect Serbian grammar and case system

#### Arabic (ar.json)
- Use Modern Standard Arabic (MSA) for broader understanding
- Right-to-left (RTL) text is handled by the app
- Preserve diacritical marks for clarity

## 📋 Key Categories

### Common Keys
Found across many pages:
- `common.save`, `common.cancel`, `common.close`
- `common.email`, `common.password`
- `common.error`, `common.success`

### Status Pages
- `status_pages.heading`, `status_pages.form.*`, `status_pages.settings.*`
- `status_pages.custom_domain.*`, `status_pages.delete.*`

### Notifications & Channels
- `notification_channels.heading`, `notification_channels.types.*`
- `notification_channels.config.*`, `notification_channels.fields.*`

### Monitors & Incidents
- `monitors.form.*`, `monitors.type.*`, `monitors.check_type.*`
- `incidents.nav.*`, `incidents.templates.*`

### User & Account
- `profile.*`, `billing.*`, `security.*`
- `teams.detail.*`, `teams.limits.*`

### UI Elements
- `notifications.frequency.*`, `analytics.config.*`
- `billing.swal.*`, `billing.trial.*`

## 🐛 Common Issues & Solutions

### Issue: Translation looks broken in the app
**Solution**: 
- Check for misplaced quotes or escape characters
- Verify HTML tags are complete (opening `<` and closing `>`)
- Ensure `{{placeholders}}` are preserved exactly
- Validate JSON syntax using an online JSON validator

### Issue: Some text still shows in English
**Solution**: The key might not be in the locale files yet. Check:
1. Is it in `en.json`?
2. Run `i18n-merge-translations-into-locales.js` to regenerate runtime locales
3. Verify the template uses `data-i18n="your.key.name"`

## 📝 Pull Request Process

1. **Fork** this repository
2. **Create a branch**: `git checkout -b improve-spanish-translations`
3. **Make changes**: Edit your language file(s)
4. **Commit**: `git commit -m "Improve Spanish translations for notification channels"`
5. **Push**: `git push origin improve-spanish-translations`
6. **Create PR**: Describe what you changed and why

### PR Checklist
- [ ] All JSON files are valid JSON (check syntax)
- [ ] No HTML tags or placeholders were removed
- [ ] Brand names remain in English
- [ ] URLs and code examples are unchanged
- [ ] Description explains the improvements/fixes

## 🔄 Syncing with Main Repository

Translation improvements are regularly synced back to the main application repository. The process:

1. Core team reviews community PRs
2. Changes are approved and merged here
3. Files are copied to the main `status` repository `translations/` folder
4. Build scripts generate updated runtime locales
5. Changes are released in the next application version

## ❓ Questions?

- **About a specific translation?** Open an issue with the key name
- **Want to translate a new language?** Create an issue to discuss
- **Found a bug in translations?** Report it with details
- **Have translation guidelines for your language?** Submit them in a PR

## 📄 License

These translation files are part of the Status Page Dashboard project and follow the same license as the main application.
See the [LICENSE](../LICENSE) file for details.

## 🙏 Thank You

We're grateful for every contribution! Translating helps make monitoring accessible to users worldwide. Whether you're fixing a single word or translating an entire language, your effort is appreciated.

---

**Current Maintainers**: Status Page Dashboard Core Team  
**Last Updated**: February 2, 2026  
**Locale Files**: `en.json`, `es.json`, `pt-br.json`, `de.json`, `fr.json`, `sr.json`, `ar.json`
