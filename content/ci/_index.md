---
title: Supported CI
weight: 25
---
{{< lead >}}
CI tools support is still under testing. Please help to report [issue](https://github.com/covergates/covergates/issues) if you encounter any problem.
{{< /lead >}}

## GitHub Action

Below is a `step` example:

```yml
- name: Report
  uses: covergates/github-actions@v1
  with:
    report-id: "Report ID"
    report-type: "go"
    report-file: "./coverage.out"
    pull-request: "true"
```

Arguments:

- `report-id` **Report ID** could be found in repository setting
- `report-type` refer to [Upload Command](/start/cli#upload-command) for more detail
- `report-file` coverage report
- `pull-request` set `true` to leave a comment on your pull request

{{< alert  style="success">}}Reach the [source code](https://github.com/covergates/github-actions) for more detail.{{< /alert  >}}

## Drone

Covergates supports Drone CI. The supported platforms are:

- Linux x64
- ARM
- ARM x64

Below is a `.drone.yml` example:

```yml
kind: pipeline
name: default
steps:
  - name: upload
    image: covergates/drone-covergates
    settings:
      report_id: bt9huh223akg00dkqseg
      report: ./coverage/lcov.info
      type: lcov
```

To leave a comment on pull request:

```yml
kind: pipeline
name: default
steps:
  - name: upload
    image: covergates/drone-covergates
    settings:
      report_id: bt9huh223akg00dkqseg
      report: ./coverage/lcov.info
      type: lcov
      comment: true
    when:
      event:
        - pull_request
```

{{< alert  style="success">}}Reach the [source code](https://github.com/covergates/drone-covergates) for more detail.{{< /alert  >}}
