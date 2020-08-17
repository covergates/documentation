---
title: Config GitHub
weight: 1
---

## Create OAuth Application

---

`covergates-server` uses OAuth2 to control user access.
To create an OAuth2 application on GitHub, please refer to [Creating an OAuth App](https://developer.github.com/apps/building-oauth-apps/creating-an-oauth-app/) for detail.

Notice that the `Authorization callback URL` should be `https://your.domain.name/login/github`. Here is an example:

![oauth](/images/github_oauth.png)

You should get the `Client ID` and `Client Secret` on your application setting page.

## Update Environment

---

Once you create an OAuth application on GitHub, you could use below environment variables to tell `covergates-server` to use it.

{{< code lang="sh" >}}
export GATES_GITHUB_CLIENT_ID="Client ID",
export GATES_GITHUB_CLIENT_SECRET="Client Secret",
export GATES_GITHUB_SERVER="https://github.com",
export GATES_GITHUB_API_SERVER="https://api.github.com",
{{< /code >}}

Restart your `covergates-server` to apply to new setting.
