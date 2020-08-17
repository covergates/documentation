---
title: Self-Hosted Server
weight: 30
---

{{< lead >}}
Covergates provides the easiest way to run self-hosted service!
{{< /lead >}}

## Getting Start

---

Get [latest released](https://github.com/covergates/covergates/releases) `covergates-server` binary.
Download `.tar.gz` for your platform and extract it to the path you like. Then run:

{{< code lang="sh" >}}
./covergates-server
{{< /code >}}

The server should start and bind to [http://localhost:8080](http://localhost:8080).

## Configuration

---

`covergates-server` uses environment variables to config.

### Config Server

You can config server address and it's base url.

- `GATES_SERVER_ADDR` Default http://localhost:8080
- `GATES_SERVER_BASE` Default /

For example:

{{< code lang="sh" >}}
export GATES_SERVER_ADDR="https://covergates.com"
{{< /code >}}

or

{{< code lang="sh" >}}
export GATES_SERVER_ADDR="http://your.domain.name"
export GATES_SERVER_BASE="/covergates"
# Server will bind to http://your.domain.name/covergates
{{< /code >}}

### Config Database

`covergates-server` uses [SQLite](https://www.sqlite.org/) by default, therefore database server is not necessary.
It will create a `core.db` under working path, all reports will save into `core.db`. You can change the database name with:

{{< code lang="sh" >}}
export GATES_DB_NAME="covergates.db"
{{< /code >}}

We also provide [PostgreSQL](https://www.postgresql.org/) as database server. Here is an example:

{{< code lang="sh" >}}
export GATES_DB_DRIVER="postgres",
export GATES_DB_HOST="127.0.0.1",
export GATES_DB_PORT="5432",
export GATES_DB_USER="postgres",
export GATES_DB_NAME="covergates",
export GATES_DB_PASSWORD="PASSWORD",
{{< /code >}}

{{< alert  style="success">}} You need to create a database on your PostgreSQL server in advance.{{< /alert >}}

### Config Git Service

`covergates-server` requires to connect with a Git service to access your source code. Supported Git service are:

- [Gitea](/server/gitea)
- [GitHub](/server/github)

Please refer to the Git service you using to learn how to config `covergates-server`.