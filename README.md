# delete-labels-from-issue v1
The GitHub Action to delete labels from issue or PR. This Action (written in JavaScript) wraps the "[Delete labels from an issue](https://octokit.github.io/rest.js/v18#issues-delete-label)" REST API.

## Inputs
### 1. `repository`
#### Required: YES

#### Default: `${{ github.repository }}`

#### Description:
The name of the repository which the issue or PR is in. E.g. '**IlyaMurashkaSharekey/delete-labels-to-issue**'.


### 2. `issue_number`
#### Required: YES

#### Default: `current`

#### Description:
The number of the issue or PR. <BR/>When no issue/PR number provided, the value is set to '**current**', the number of the issue/PR that triggers current workflow run will be used by default. If do not find a valid number or the provided number is invalid, the "**Not Found**" error returned.


### 3. `labels`
#### Required: YES

#### Description:
The labels you want to delete. You can provide one or more labels.


### 4. `token`
#### Default: `${{ github.token }}`

#### Description:
Personal access token (PAT) used to authenticate.
##


## Example workflows
### Delete a single label
```yaml
jobs:
  job1:
    runs-on: ubuntu-latest
    steps:      
      - name: Delete labels
        uses: IlyaMurashkaSharekey/delete-labels-from-issue@v1
        with:
          issue_number: 5
          labels: label-01
```

### Delete multiple labels
```yaml
jobs:
  job1:
    runs-on: ubuntu-latest
    steps:      
      - name: Delete labels
        uses: IlyaMurashkaSharekey/delete-labels-from-issue@v1
        with:
          issue_number: 5
          labels: |
            label-01
            label-02
```
##

