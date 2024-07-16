# Run Script

A composite custom github action that runs given script in different languages.

## Parameters

| Name          | Description                                        | Required | Default         |
|---------------|----------------------------------------------------|----------|-----------------|
| lang          | Language used for script. Possible values: `shell`, `python`, `java`, `javascript` | Yes      |                 |
| dir           | Path of the script.                                | No       | `.`             |
| name          | Name of the script including file extension        | Yes      |                 |

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
