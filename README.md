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
    }
  ],
  "beta": {
    "version": "4.6.1-beta.3",
    "downloadUrlPhp": "https://github.com/exampleuser/abc_example/archive/4.6.1-beta.3.zip",
    "downloadUrlTxt": "https://github.com/exampleuser/abc_example/releases/download/4.6.1-beta.3/abc_example_v4.6.1-beta.3_zip.txt"
  },
  "stable": {
    "version": "4.6.0",
    "downloadUrlPhp": "https://github.com/exampleuser/abc_example/archive/4.6.0.zip",
    "downloadUrlTxt": "https://github.com/exampleuser/abc_example/releases/download/4.6.0/abc_example_v4.6.0_zip.txt"
  },
  "legacy": [
    {
      "4.5": {
        "version": "v4.5.0.0-beta.4",
        "downloadUrlPhp": "https://github.com/exampleuser/abc_example/archive/v4.5.0.0-beta.4.tar.gz",
        "downloadUrlTxt": "https://github.com/exampleuser/abc_example/archive/v4.5.0.0-beta.4.zip"
      }
    }
  ]
}
```

We also provide [a JSON template](https://raw.githubusercontent.com/textpattern/textpattern-curated-plugins-list/master/template.json) as a useful starting point.

Explanation TODO

## License

Licensed under MIT license.
