---
title: Config GitLab
weight: 3
---

## Create OAuth Application

---

`covergates-server` uses OAuth2 to control user access.
To create an OAuth2 application on GitLab, navigate `http://your.gitlab.domain/profile/applications` on your GitLab website.

Create a new application as shown below:

![oauth](/images/gitlab_oauth.png)

{{< alert  style="success">}} Replace `http://localhost:8080/login/gitlab` to your Covergates URL, such as `http://your.domain.name/login/gitlab`{{< /alert >}}

Notice that covergates requires below scopes:

- api
- read_user
- read_api
- read_repository
- profile
- email

You should get your **Client ID** and **Client Secret** like:

![client](/images/gitlab_client.png)

## Update Environment

---

Once you create an OAuth application on GitLab, you could use below environment variables to tell `covergates-server` to use it.

{{< code lang="sh" >}}
export GATES_GITLAB_CLIENT_ID="68e4d83d0093dcb0e862eb9b4dbdfbb7b2e993e9f0259a66017f18995d0cdaf7",
export GATES_GITLAB_CLIENT_SECRET="ed989a0a94ecb7c0520f764f78ff3ff751bab198ddfebdb39f9bdf2b9aa958f7",
export GATES_GITLAB_SERVER="http://localhost",
export GATES_GITLAB_SKIP_VERITY="true"
{{< /code >}}

{{< alert  style="success">}} Replace `GATES_GITLAB_CLIENT_ID`, `GATES_GITLAB_CLIENT_SECRET` and `GATES_GITLAB_SERVER` to the value you acquire on previous step.{{< /alert >}}

Restart your `covergates-server` to apply to new setting.
