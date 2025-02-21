#NOTICE - This repo was copied from https://github.shared-services.aws.tri.global/infrastructure/run-script ref: TRI-40381

# Run Script

A composite custom github action that runs given script in different languages and sets the output to output.txt

## Parameters

| Name          | Description                                        | Required | Default         |
|---------------|----------------------------------------------------|----------|-----------------|
| path           | Path of the script/ directory that the scripts are located                                | No       | `.`             |

## Example

```yaml
jobs:
  test:
    runs-on: [self-hosted]

    steps:
    - name: Check out repository code
      uses: actions/checkout@v3

    - name: Run script
      id: run_script
      uses: infrastructure/run-script@v0.0.1
      with:
        path: "."
    - name: Display Output
      run: echo "Output: ${{ steps.run_script.outputs.stdout }}"
```
