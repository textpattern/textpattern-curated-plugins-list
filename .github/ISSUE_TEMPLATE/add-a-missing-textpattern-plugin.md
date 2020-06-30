---
name: Add a missing Textpattern plugin
about: Use this form to suggest a Textpattern plugin to be added to the plugins website.
title: "[ADD] xxxxx"
labels: plugin-add
---

**Note:** Please ensure you have read the [README](https://github.com/textpattern/textpattern-curated-plugins-list/blob/master/README.md) file prior to filing this issue.

**Name of plugin (including author prefix)**

xxx_xxxxxx

**Please complete as much of the JSON template below as is possible/relevant**

```json
{
  "name": "{prefix_plugin-name}",
  "repositories": [
    {
      "repoType": "{repo-site}",
      "repoUrl": "{repo-site-username}/{repo-project-name}"
    }
  ],
  "beta": {
    "version": "{semver}",
    "maxTxpCompatibility": "{ver-of-textpattern}",
    "date": "{yyyy}-{mm}-{dd}",
    "downloadUrlPhp": "{url-of-php-plugin}",
    "downloadUrlTxt": "{url-of-txt-plugin}"
  },
  "stable": {
    "version": "{semver}",
    "maxTxpCompatibility": "{ver-of-textpattern}",
    "date": "{yyyy}-{mm}-{dd}",
    "downloadUrlPhp": "{url-of-php-plugin}",
    "downloadUrlTxt": "{url-of-txt-plugin}"
  },
  "legacy": [
    {
      "4.6": {
        "version": "{semver}",
        "date": "{yyyy}-{mm}-{dd}",
        "downloadUrlPhp": "{url-of-php-plugin}",
        "downloadUrlTxt": "{url-of-txt-plugin}"
      }
    },
    {
      "4.5": {
        "version": "{semver}",
        "date": "{yyyy}-{mm}-{dd}",
        "downloadUrlPhp": "{url-of-php-plugin}",
        "downloadUrlTxt": "{url-of-txt-plugin}"
      }
    }
  ]
}
```

**Brief description of plugin (optional)**
