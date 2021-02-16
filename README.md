# textpattern-curated-plugins-list

[![Build Status](https://travis-ci.com/textpattern/textpattern-curated-plugins-list.svg)](https://travis-ci.com/textpattern/textpattern-curated-plugins-list)

A curated list of [Textpattern CMS](https://textpattern.com) plugins listed in the [Textpattern plugins website](https://github.com/textpattern/textpattern-plugins-website).

## JSON structure

Each plugin has a JSON-formatted 'library card', located within the `library-of-plugins` directory of this repository.

The Textpattern plugins website digests the information for each card to provide the relevant details of the plugin. Each card expects a set of [required entries](#required-entries) plus any [optional entries](#optional-entries) as appropriate. **It is recommended** that you complete as many fields as possible in the JSON file, as this helps provide the most information to users within the Textpattern plugins site and assists with ongoing maintenance.

### Example structure

```JSON
{
  "name": "abc_example",
  "repositories": [
    {
      "repoType": "homepage",
      "repoUrl": "https://example.com/abc_example.html"
    },
    {
      "repoType": "github",
      "repoUrl": "https://github.com/exampleuser/abc_example"
    },
    {
      "repoType": "bitbucket",
      "repoUrl": "https://bitbucket.org/exampleuser/abc_example"
    },
    {
      "repoType": "gitlab",
      "repoUrl": "https://gitlab.com/exampleuser/abc_example"
    }
  ],
  "require": {
    "abc_extra_example": ">=2.0.0"
  },
  "beta": {
    "version": "3.7.1-beta.3",
    "datePublished": "2020-06-26",
    "downloadUrlPhp": "https://github.com/exampleuser/abc_example/archive/3.7.1-beta.3.zip",
    "phpHasManifest": 1
  },
  "stable": {
    "version": "3.7.0",
    "datePublished": "2020-02-14",
    "downloadUrlTxt": "https://github.com/exampleuser/abc_example/releases/download/3.7.0/abc_example_v3.7.0.txt",
    "downloadUrlPhp": "https://github.com/exampleuser/abc_example/archive/3.7.0.zip",
    "phpHasManifest": 1
  },
  "legacy": [
    {
      "4.6": {
        "version": "v2.5.3",
        "datePublished": "2018-10-18",
        "downloadUrlTxt": "https://github.com/exampleuser/abc_example/archive/v2.5.3.txt",
        "downloadUrlPhp": "https://github.com/exampleuser/abc_example/archive/v2.5.3.tar.gz",
        "phpHasManifest": 0
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

A [JSON template](https://raw.githubusercontent.com/textpattern/textpattern-curated-plugins-list/master/template.json) is provided as a useful starting point.

### Required entries

* `name`:\
  The name of the plugin, including the [plugin author prefix](https://docs.textpattern.com/brand/author-prefixes-and-registration).
* `stable` and/or `beta`:\
  At least one of either `stable` and/or `beta` nodes need to be stated. If the plugin has no official `stable` release, then `beta` release will take precedence.
* `version`:\
  `stable`, `beta` and `legacy` nodes each require a `version` entry in `semver` format (e.g. `1.3.8`).
* `downloadUrlTxt` and/or `downloadUrlPhp`:\
  `stable`, `beta` and `legacy` nodes each require at least one of either `downloadUrlTxt` and/or `downloadUrlPhp` nodes to be stated. `downloadUrlTxt` refers to the download URL of the TXT-encoded version of the plugin, `downloadUrlPhp` refers to the download URL of the PHP version of the plugin.
* `phpHasManifest`:\
  `stable`, `beta` and `legacy` nodes each require a `phpHasManifest` entry if `downloadUrlPhp` nodes are stated. Boolean values (`1` if the `manifest.json` file exists, otherwise `0`). If a `phpHasManifest` entry is missing, it is assumed the `manifest.json` file does not exist for that release. When only `downloadUrlTxt` is stated, the `phpHasManifest` entry is not required (and is ignored, if present). For more information on plugin manifest files, [see below](#manifests-for-php-versions-of-plugins).

### Example minimum structure

This is the minimum that is required in each JSON file. Note that, as described above, `stable` or `beta` could be stated on line 3. `phpHasManifest` is required when a `downloadUrlPhp` entry is provided (not required if only a `downloadUrlTxt` is provided):

```JSON
{
  "name": "abc_example",
  "stable": {
    "version": "3.7.0",
    "downloadUrlPhp": "https://github.com/exampleuser/abc_example/archive/3.7.0.zip",
    "phpHasManifest": 1
  }
}
```

### Optional (but recommended) entries

* `repositories`:\
  One or more code repositories where the the project is maintained. For each entry, a `repoType` and `repoUrl` must be provided. For `repoType` expected values are either `homepage` (i.e. page on an author's website specifically about the plugin), `github`, `bitbucket` or `gitlab`.
* `require`:\
  If this plugin requires another plugin to be installed in order to work, state the plugin and version requirements.
* `datePublished`:\
  Release date (in ISO 8601 `yyyy-mm-dd` format) of version.
* `legacy`:\
  One or more releases that are specifically for older versions of Textpattern. Each legacy release must be labelled with the maximum version series of Textpattern it worked with. For example `4.6`.

### Manifests for PHP versions of plugins

In order to allow PHP versions of a plugin to be upgraded via auto-update functionality directly within (future) Textpattern, a `manifest.json` file in the following format is expected to reside within the root directory of the plugin folder:

```JSON
{
  "name": "abc_example",
  "description": "An example plugin description here.",
  "version": "0.1.0",
  "type": 5,
  "author": "Aaron A. Aardvark",
  "author_uri": "https://example.com/",
  "order": 5,
  "flags": 2,
  "help": {"file" : ["./README.textile"]},
  "code": {"file" : ["./abc_example.php"]},
  "textpack": {"file" : ["./textpack.txp"]},
  "data": {"file" : ["./data.txp"]}
}
```

Plugins that do not follow the above format, and/or that do not have an alternative TXT file available, will be excluded from auto-update functionality.

### Linting

You can run a linter over the JSON files to check validity as follows (requires [Node.js](https://nodejs.org/)):

```ShellSession
$ cd textpattern-curated-plugins-list
$ npm install
$ npm run jsonlint
```

## License

Licensed under [MIT license](https://github.com/textpattern/textpattern-curated-plugins-list/blob/master/LICENSE).
