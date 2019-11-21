# sanity-plugin-language-switcher

Sanity plugin providing basic select dropdown for languages instead of multi-select.

# Usage

`sanity.json`

```
{
  "name": "part:language-switcher/config",
  "path": "./parts/languageSwitcherConfig.js"
}
```

`languageSwitcherConfig.js`

```
export default {
  supportedLanguages: [{
    id: 'en',
    title: 'English',
  }, {
    id: 'fr',
    title: 'French',
  }],
  filterField: (enclosingType, field, selectedLanguageIds) => {
    return (
      !enclosingType.name.startsWith("locale") ||
      selectedLanguageIds.includes(field.name)
    )
  },
}
```
