---
title: Config Gitea
weight: 3
---

## Create OAuth Application

---

`covergates-server` uses OAuth2 to control user access.
To create an OAuth2 application on Gitea, navigate `Settings > Applications` on your Gitea website.
The URL would be:

```sh
# Replace http://localhost:3000 to your Gitea URL
http://localhost:3000/user/settings/applications
```

Create a new application as shown below:

![oauth](/images/gitea_oauth.png)

{{< alert  style="success">}} Replace `http://localhost:8080/login/gitea` to your Covergates URL, such as `http://your.domain.name/login/gitea`{{< /alert >}}

You should get your **Client ID** and **Client Secret** like:

![client](/images/gitea_client.png)

## Update Environment

---

Once you create an OAuth application on Gitea, you could use below environment variables to tell `covergates-server` to use it.

{{< code lang="sh" >}}
export GATES_GITEA_CLIENT_ID="2c591d86-b26a-416a-9b1c-4bc2ea770033",
export GATES_GITEA_CLIENT_SECRET="USBsFNPJmlJg1VPx-t5Pwwo2hZ9lDDXUEEP-Jebzm-w=",
export GATES_GITEA_SERVER="http://localhost:3000",
export GATES_GITEA_SKIP_VERITY="true"
{{< /code >}}

{{< alert  style="success">}} Replace `GATES_GITEA_CLIENT_ID`, `GATES_GITEA_CLIENT_SECRET` and `GATES_GITEA_SERVER` to the value you acquire on previous step.{{< /alert >}}

Restart your `covergates-server` to apply to new setting.
