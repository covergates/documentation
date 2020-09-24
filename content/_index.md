---
title: Covergates
---

{{< lead >}}
Welcome to Covergates User Guide!
{{< /lead >}}

## What is Covergates?

---

Covergates is a self-hosted coverage reports management web service.
It's an alternative to services like:

- [Code Climate](https://codeclimate.com/)
- [Codecov](https://codecov.io/)
- [Coveralls](https://coveralls.io/)

The goal of this project is to provide an easiest way
to deploy a self-hosted service to track code coverage.
You don't need to have **root permission**, **network connection** or even **database server**
to run covergates.
Covergates is built with **[Go](https://golang.org/)** language,
therefore it provides an independent binary distribution across all platforms that Go supports.
It includes Linux, Windows and macOS.

## Features

---

- Git Service Support

    - Gitea
    - GitHub

- Languages Support

    - Go
    - Python
    - Ruby
    - Perl
    - C / C++
    - Javascript
    - TypeScript

- CI Tools

    - GitHub Action
    - Drone

- Database

    - SQLite
    - PostgreSQL

- Web Service

    - Source Code Coverage Highlight

    - Repository Setting Dashboard

    - Commits History

    - Promotions

        - Coverage Badge [![badge](https://covergates.com/api/v1/reports/bsi5dvi23akg00a0tgl0/badge?)](https://covergates.com/report/github/covergates/covergates)
        - Repository Status Card

            [![card](https://covergates.com/api/v1/reports/bsi5dvi23akg00a0tgl0/card)](https://covergates.com/report/github/covergates/covergates)


## Coming Soon

---

<i class='fas fa-wrench'></i> We are working on:

- Git Service

    - GitLab Support

- Language Support

    - Java
    - Others, [let us know the language you want!](https://github.com/covergates/covergates/issues)

- Database

    - MySQL
