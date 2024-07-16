# Run Script

A composite custom github action that runs given script in different languages.

## Parameters

There are two parameters required to use this action:

* `lang`: (Required) Language used for script. Currently it supports `shell`, `python`, `java` and `javascript`.
* `dir`: Directory path of the script. By default it's set to root of the repository you are using this action for.
* `name`: (Required) Name of the script you want to run, including the file extension. (i.e `my_script.sh`)

## Example

```yaml
jobs:
  test:
    runs-on: [self-hosted]

    steps:
    - name: Check out repository code
      uses: actions/checkout@v3

    - name: Run script
      uses: infrastructure/run-script@v0.0.1
      with:
        lang: python
        name: test.py
```
