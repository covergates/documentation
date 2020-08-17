---
title: Repository Setting
weight: 30
---
{{< lead >}}
You could config repository on setting page.
{{< /lead >}}

## Filter Path

---

**Filter** takes regular expressions and trims the path. Take `Go` coverage report for example:

```sh
mode: set
github.com/covergates/covergates/modules/report/report.go:22.100,24.45 2 1
github.com/covergates/covergates/modules/report/report.go:27.2,28.45 2 1
github.com/covergates/covergates/modules/report/report.go:39.2,39.22 1 1
github.com/covergates/covergates/modules/report/report.go:47.2,48.45 2 1
github.com/covergates/covergates/modules/report/report.go:52.2,55.8 1 1
github.com/covergates/covergates/modules/report/report.go:24.45,26.3 1 1
github.com/covergates/covergates/modules/report/report.go:28.45,33.32 2 1
github.com/covergates/covergates/modules/report/report.go:37.3,37.38 1 1
github.com/covergates/covergates/modules/report/report.go:33.32,36.4 2 1
```

You could remove `github.com/covergates/covergates` with setting:

![filter](/images/setting_filter.png)

{{< alert  style="success">}}We are working on default filters, you could refer to [GitHub](https://github.com/covergates/covergates) for the progress or help us by [contributing](https://github.com/covergates/covergates/blob/master/CONTRIBUTING.md).{{< /alert  >}}
