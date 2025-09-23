# gh-manifest
A "package lock"-style manifest for declaratively installing plugins.
## Usage
To save the current list of installed extensions to the manifest, run:
```bash
gh manifest save
```
When saving with the `--commit` flag (or with the `commitOnSave` option set to `true`), `manifest` will automatically commit the changes to the manifest to whatever git tree is currently tracking it. The commit message can be changed with the `--message` flag (or with the `commitMessage` option).

To read and install the list of installed extensions from the manifest, run:
```bash
gh manifest restore
```

Both can be used with `--file` to specifiy a specific manifest to read from or modify. Otherwise, it will default to a file named `manifest` in the same directory used by `gh`.
If your extension list is available online as a raw file, you can install from that manifest with:
```bash
gh manifest restore --file <(curl -Ns https://example.com)
```

### Configuration
`gh-manifest` has a few configuration options, mostly to permanently enable some flags, which you can set using `gh manifest set <key> <value>`. See `gh manifest --help` for the full list of options.
