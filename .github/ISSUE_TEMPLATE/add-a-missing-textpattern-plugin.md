---
name: Add a missing Textpattern plugin
about: Use this form to suggest a Textpattern plugin to be added to the plugins website.
title: "[ADD] xxxxx"
labels: plugin-add
---

**Note:** Please ensure you have read the [README](https://github.com/textpattern/textpattern-curated-plugins-list/blob/master/README.md) file prior to filing this issue.

**Name of plugin (including author prefix)**

xxx_xxxxx

**Please complete as much of the JSON template below as is possible/relevant**

```json
{
  "name": "{prefix_plugin-name}",
  "repositories": [
    {
      "repoType": "{repo-site}",
      "repoUrl": "{repo-site-username}/{repo-project-name}"
    },
    {
      "repoType": "homepage",
      "repoUrl": "{url-of-plugin-homepage}"
    }
  ],
  "beta": {
    "version": "{semver}",
    "datePublished": "{yyyy}-{mm}-{dd}",
    "downloadUrlPhp": "{url-of-php-plugin}",
    "downloadUrlTxt": "{url-of-txt-plugin}"
  },
  "stable": {
    "version": "{semver}",
    "datePublished": "{yyyy}-{mm}-{dd}",
    "downloadUrlPhp": "{url-of-php-plugin}",
    "downloadUrlTxt": "{url-of-txt-plugin}"
  },
  "legacy": [
    {
      "4.6": {
        "version": "{semver}",
        "datePublished": "{yyyy}-{mm}-{dd}",
        "downloadUrlPhp": "{url-of-php-plugin}",
        "downloadUrlTxt": "{url-of-txt-plugin}"
      }
    },
    {
      "4.5": {
        "version": "{semver}",
        "datePublished": "{yyyy}-{mm}-{dd}",
        "downloadUrlPhp": "{url-of-php-plugin}",
        "downloadUrlTxt": "{url-of-txt-plugin}"
      }
    }
  ]
}
```

**Textpattern min and max compatibility of latest plugin version, if known (x all that apply)**

Textpattern version compatibility:

- [ ] 4.8
- [ ] 4.7
- [ ] 4.6
- [ ] 4.5

**Brief description of plugin (optional)**
