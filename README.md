# textpattern-curated-plugins-list

A curated list of Textpattern plugins, in JSON format. Data will be utilized in tandem with the upcoming [Textpattern plugins website](https://github.com/textpattern/textpattern-plugins-website).

## JSON structure (TBC)

Description TODO

### Example structure (TBC)

```JSON
{
  "name": "abc_example",
  "repositories": [
    {
      "repoType": "github.com",
      "repoUrlStub": "exampleuser/abc_example"
    }
  ],
  "beta": {
    "version": "4.6.1-beta.3",
    "downloadUrlPhp": "https://github.com/exampleuser/abc_example/archive/4.6.0-beta.1.zip",
    "downloadUrlTxt": "https://github.com/exampleuser/abc_example/releases/download/4.6.0-beta.3/abc_example_v4.6.0-beta.1_zip.txt"
  },
  "stable": {
    "version": "4.6.0",
    "downloadUrlPhp": "https://github.com/exampleuser/abc_example/archive/4.6.0.zip",
    "downloadUrlTxt": "https://github.com/exampleuser/abc_example/releases/download/4.6.0/abc_example_v4.6.0_zip.txt"
  },
  "legacy": {
      "4.5": {
        "version": "v4.5.0.0-beta.4",
        "downloadUrlPhp": "https://github.com/exampleuser/abc_example/archive/v4.5.0.0-beta.4.tar.gz",
        "downloadUrlTxt": "https://github.com/exampleuser/abc_example/archive/v4.5.0.0-beta.4.zip"
      }
  }
}
```

Explanation TODO

## License

Licensed under MIT license.
