# textpattern-curated-plugins-list

A curated list of Textpattern plugins, in JSON format. Data is utilized in the [Textpattern plugins website](https://github.com/textpattern/textpattern-plugins-website).

## JSON structure (TBC)

Each curated plugin has a JSON-formatted 'library card', located within the `library-of-plugins` directory of this GitHub repository.

**Full description TODO.**

### Example structure

```JSON
{
  "name": "abc_example",
  "repositories": [
    {
      "repoType": "github",
      "repoUrl": "https://github.com/exampleuser/abc_example"
    },
    {
      "repoType": "bitbucket",
      "repoUrl": "https://bitbucket.org/exampleuser/abc_example"
    },
    {
      "repoType": "homepage",
      "repoUrl": "https://example.com/abc_example.html"
    }
  ],
  "beta": {
    "version": "3.7.1-beta.3",
    "datePublished": "2020-06-26",
    "downloadUrlPhp": "https://github.com/exampleuser/abc_example/archive/3.7.1-beta.3.zip"
  },
  "stable": {
    "version": "3.7.0",
    "datePublished": "2020-02-14",
    "downloadUrlPhp": "https://github.com/exampleuser/abc_example/archive/3.7.0.zip",
    "downloadUrlTxt": "https://github.com/exampleuser/abc_example/releases/download/3.7.0/abc_example_v3.7.0.txt"
  },
  "legacy": [
    {
      "4.6": {
        "version": "v2.5.3",
        "datePublished": "2018-10-18",
        "downloadUrlPhp": "https://github.com/exampleuser/abc_example/archive/v2.5.3.tar.gz",
        "downloadUrlTxt": "https://github.com/exampleuser/abc_example/archive/v2.5.3.txt"
      }
    },
    {
      "4.5": {
        "version": "v1.4.0-beta.4",
        "downloadUrlTxt": "https://github.com/exampleuser/abc_example/archive/v1.4.0-beta.4_zip.txt"
      }
    }
  ]
}
```

We also provide [a JSON template](https://raw.githubusercontent.com/textpattern/textpattern-curated-plugins-list/master/template.json) as a useful starting point.

### Required entries

* `name`\
  The name of the plugin, including the plugin author prefix.
* `stable` and/or `beta`\
  At least one of either `stable` and/or `beta` nodes need to be stated. If the plugin has no official `stable` release, then `beta` release will take precedence.
* `version`\
  `stable`, `beta` and `legacy` nodes each require a `version` entry in `semver` format (e.g. `1.3.8`).
* `downloadUrlPhp` and/or `downloadUrlTxt`\
  `stable`, `beta` and `legacy` nodes each require at least one of either `downloadUrlPhp` and/or `downloadUrlTxt` nodes to be stated. `downloadUrlPhp` refers to download URL of the PHP version of the plugin, `downloadUrlTxt` refers to the download URL of the TXT-compiled version of the plugin.


### Example absolute minimum structure

This is the absolutely minimum that is required in each JSON file. Note that, as described above, `stable` or `beta` could be stated on line 3:

```JSON
{
  "name": "abc_example",
  "stable": {
    "version": "3.7.0",
    "downloadUrlPhp": "https://github.com/exampleuser/abc_example/archive/3.7.0.zip"
  }
}
```

### Optional entries

* `repositories`\
  One or more code repositories where the the project is maintained. For each entry, a `repoType` and `repoUrl` must be provided. For `repoType` expected values are either `homepage` (i.e. page on an author's website specifically about the plugin), `github`, `bitbucket` or `gitlab`.
* `datePublished`\
  Release date (in ISO 8601 `yyyy-mm-dd` format) of version.
* `legacy`\
  One or more releases that are specifically for older versions of Textpattern. Each legacy release must be labelled with the maximum version of Textpattern it worked with. For example `4.6`.

## License

Licensed under MIT license.
