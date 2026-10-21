# Stidy website

Static site (no build step) hosted on GitHub Pages: landing page, privacy policy, terms of use and sale. French at the root, English under `/en/`.

## Before publishing: fill the placeholders

Replace in every `.html` file:

| Token | Meaning |
|---|---|
| `{{PUBLISHER_NAME}}` | Legal name of the publisher (person or company) |
| `{{PUBLISHER_ADDRESS}}` | Postal address (legally required for the publisher) |
| `{{CONTACT_EMAIL}}` | Public contact / privacy email |
| `{{MEDIATOR}}` | Consumer mediator (name + website), required for French B2C sales |

```bash
grep -rl '{{' --include=*.html . | xargs sed -i '' \
  -e 's|{{PUBLISHER_NAME}}|...|g' -e 's|{{PUBLISHER_ADDRESS}}|...|g' \
  -e 's|{{CONTACT_EMAIL}}|...|g' -e 's|{{MEDIATOR}}|...|g'
```

## Preview

`python3 -m http.server 8000`
