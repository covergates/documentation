---
title: Command Line Tool
weight: 20
---

## The Command

---

You can acquire `covergates` command line tool for [releases](https://github.com/covergates/covergates/releases) page.
Download the `.tar.gz` for your platform and extract it to somewhere in your `PATH`. You test it by running:

{{< code lang="sh">}}
covergates help
{{< /code >}}

```sh
NAME:
   covergate - A new cli application

USAGE:
   covergates [global options] command [command options] [arguments...]

VERSION:
   0.0

COMMANDS:
   upload   upload coverage report
   comment  leave a report summary comment
   help, h  Shows a list of commands or help for one command

GLOBAL OPTIONS:
   --url value    api service url (default: "https://covergates.com/api/v1") [$API_URL]
   --help, -h     show help (default: false)
   --version, -v  print the version (default: false)
```

By default, `covergates` will connect to `https://covergates.com/api/v1`. You can change it to your self-hosted server with:

{{< code lang="sh">}}
export API_URL="https://your.domain.name/api/v1"
{{< /code >}}

You can also rebuild the `covergates` to permanently change the `API_URL`, please refer to [README.md](https://github.com/covergates/covergates/blob/master/README.md) for more detail.

## Upload Command

---

```sh
NAME:
   covergates upload - upload coverage report

USAGE:
   covergates upload [command options] report

OPTIONS:
   --report value  report id [$REPORT_ID]
   --type value    report type
   --branch value  branch to upload the report [$GITHUB_HEAD_REF, $DRONE_SOURCE_BRANCH]
   --help, -h      show help (default: false)
```
`covergates upload` helps you upload coverage reports. It requires at least 3 arguments:

- `--report`: Report ID
- `--type`: Report Type
- `report`: Report Path

You could omit `--report` once you setup `REPORT_ID` environment.

The supported report type `--type` are:

{{< table >}}
|Language|Type|Format|Report Name Example|
|:--:|:--:|:--:|:--:|
|Go|`go`|cover|coverage.out|
|Perl|`perl`|Devel::Cover|core_db|
|Python|`python`|Coverage.py - xml|coverage.xml|
|Ruby|`ruby`|SimpleCov - RSpec|.resultset.json|
|C / C++|`lcov`|lcov|lcov.info|
|Javascript / Typescript|`lcov`|lcov|lcov.info|
{{< /table >}}

## Comment Command

---

```sh
NAME:
   covergates comment - leave a report summary comment

USAGE:
   covergates comment [command options] [arguments...]

OPTIONS:
   --report value  report id [$REPORT_ID]
   --number value  pull request number [$DRONE_PULL_REQUEST, $PULL_REQUEST]
   --help, -h      show help (default: false)
```

`covergates comment` will leave a brief summary on your pull request.
Here is an example:

![comment](/images/pr_comment.png)

{{< panel title="Notice" style="primary" >}} The command may require running `covergates upload` with `--branch` to work. {{< /panel >}}
