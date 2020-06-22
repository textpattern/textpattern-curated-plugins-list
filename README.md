# textpattern-curated-plugins-list

A curated list of Textpattern plugins, in JSON format. Data is utilized in the [Textpattern plugins website](https://github.com/textpattern/textpattern-plugins-website).

## JSON structure (TBC)

Each curated plugin has a JSON-formatted 'library card', located within the `library-of-plugins` directory of this GitHub repository.

Description TODO

### Example structure

```JSON
{
  "name": "abc_example",
  "repositories": [
    {
      "repoType": "github",
      "repoUrlStub": "exampleuser/abc_example"
    },
    {
      "repoType": "bitbucket",
      "repoUrlStub": "exampleuser/abc_example"
    }
  ],
  "beta": {
    "version": "3.7.1-beta.3",
    "downloadUrlPhp": "https://github.com/exampleuser/abc_example/archive/3.7.1-beta.3.zip",
    "downloadUrlTxt": "https://github.com/exampleuser/abc_example/releases/download/3.7.1-beta.3/abc_example_v3.7.1-beta.3_zip.txt"
  },
  "stable": {
    "version": "3.7.0",
    "downloadUrlPhp": "https://github.com/exampleuser/abc_example/archive/3.7.0.zip",
    "downloadUrlTxt": "https://github.com/exampleuser/abc_example/releases/download/4.6.0/abc_example_v3.7.0_zip.txt"
  },
  "legacy": [
    {
      "4.6": {
        "version": "v2.5.3",
        "downloadUrlPhp": "https://github.com/exampleuser/abc_example/archive/v2.5.3.tar.gz",
        "downloadUrlTxt": "https://github.com/exampleuser/abc_example/archive/v2.5.3.zip"
      }
    },
    {
      "4.5": {
        "version": "v1.4.0-beta.4",
        "downloadUrlTxt": "https://github.com/exampleuser/abc_example/archive/v1.4.0-beta.4.zip"
      }
    }
  ]
}
```

We also provide [a JSON template](https://raw.githubusercontent.com/textpattern/textpattern-curated-plugins-list/master/template.json) as a useful starting point.

### Required entries

`name`: the name of the plugin, including the plugin author prefix.

`stable` and/or `beta`: at least one of either `stable` and/or `beta` needs to be stated. If the plugin has no official `stable` release then `beta` release will take precedence.

TODO

### optional entries

`repositories`: one or more code repositories where the the project is maintained.

`legacy`: one or more releases that are specifically for older versions of Textpattern. Each legacy release must be labelled with the maximum version of Textpattern it worked with. For example `4.6`.

TODO

## License

Licensed under MIT license.
