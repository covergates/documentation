---
title: Quick Start
weight: 10
---

{{< lead >}}
This tutorial will access to [https://covergates.com](https://covergates.com/).
If you are using self-hosted version, please replace [https://covergates.com/](https://covergates.com/)
to your self-hosted server URL.
{{< /lead >}}

## Fundamental Workflow

---

1. Sign up [Covergates](https://covergates.com/) with your [GitHub](https://github.com/) or [Gitea](https://gitea.com/) account.
2. Navigate [https://covergates.com/repo](https://covergates.com/repo) to the list of your repositories.
3. Click **ACTIVATE** button to activate the repository for uploading coverage reports.
4. Go to **SETTING** tag, you can update report path filter and get your **Report ID**

    {{< alert  style="success">}}To get more information about repository setting, please refer to [Repository Setting](/start/setting){{< /alert  >}}
5. Run testing for your language and generate coverage report. You can refer to [Supported Language](/language) for more detail.
6. Download the [latest released](https://github.com/covergates/covergates/releases) `covergates` command line tool for your platform.
Once downloaded, the binary can run directly. You could put it to somewhere in your `PATH`.
7. Upload your report by running `covergates upload`, for example:

    {{< code lang="sh" >}}
    covergates upload --report <Report ID> --type go ./coverage.out
    {{< /code >}}

    or for self-hosted server

    {{< code lang="sh" >}}
    export REPORT_ID="Report ID"
    export API_URL="http://your.domain.name/api/v1"
    covergates upload --type go ./coverage.out
    {{< /code >}}

    {{< alert  style="success">}} You can refer to [Command Line Tool](/start/cli) for more options.{{< /alert >}}
8. Congratulation! <i class="far fa-laugh-squint"></i> Now you can navigate your repository page to see your report!