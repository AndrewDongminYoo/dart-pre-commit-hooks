# Dart Format `pre-commit`

[`pre-commit`](https://pre-commit.com) hook for formatting Dart files.

## Installation

1. Install `pre-commit` first.

    [pre-commit installation](https://pre-commit.com/#install)

    ```shell
    # You Can Choose One from these!!

    > brew install pre-commit
    > pip install pre-commit
    > conda install -c conda-forge pre-commit
    ```

2. Add the following in your `.pre-commit-config.yaml` in root directory:

    ```yaml
    - repo: https://github.com/AndrewDongminYoo/dart-pre-commit-hooks
      rev: main
      hooks:
        - id: dart-format
        # id: flutter-analyze is also available. It executes flutter analyze.
    ```

    (Optional) Run `pre-commit autoupdate` for using the latest version (commit SHA) of this repo.

    [WARNING] The 'rev' field of repo 'https://github.com/AndrewDongminYoo/dart-pre-commit-hooks' appears to be a mutable reference (moving tag / branch).  Mutable references are never updated after first install and are not supported.  See https://pre-commit.com/#using-the-latest-version-for-a-repository for more details.  Hint: `pre-commit autoupdate` often fixes this.

3. Run pre-commit install to set up the git hook scripts

    ```shell
    > pre-commit install
    pre-commit installed at .git/hooks/pre-commit
    ```

    - Now you can run `pre-commit` automatically on `git commit`.

4. (Optional) Run against all the files.

    ```shell
    > pre-commit run --all-files
    ```

## Configuration

You can also include/exclude some files (defaults to only `.dart`, is a pattern):

```yaml
- repo: https://github.com/AndrewDongminYoo/dart-pre-commit-hooks
  rev: main
  hooks:
    - id: dart-format
      files: lib/* # Only format source files (default is ".dart")
      exclude: lib/gen/l10n/app_localizations_ko.dart # Exclude utils
      args: [--line-length=100] # Pass --line-length=100 parameter to dart format
```

## NOTE

Also see [Flutter Format `pre-commit`](https://github.com/Cretezy/flutter-format-pre-commit) for formatting Flutter code.

This Project is forked from [Createzy's `flutter-format-pre-commit`](https://github.com/Cretezy/flutter-format-pre-commit) to support Dart formatting. Note that the tool uses `dartfmt`, which is now deprecated.
