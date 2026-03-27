<p align="center">
  <br>
  <img src="https://raw.githubusercontent.com/kilnx-org/kilnx/main/.github/banner.svg" alt="kilnx" width="800"/>
  <br><br>
</p>

<p align="center">
  Declarative backend language that compiles to a single binary.<br>
  27 keywords. Zero framework. SQL is the query language. HTML is the output.
</p>

<p align="center">
  <a href="https://kilnx.dev"><strong>kilnx.dev</strong></a> &nbsp;&bull;&nbsp;
  <a href="https://github.com/kilnx-org/kilnx">Source</a> &nbsp;&bull;&nbsp;
  <a href="https://github.com/kilnx-org/kilnx/blob/main/GRAMMAR.md">Grammar</a> &nbsp;&bull;&nbsp;
  <a href="https://github.com/kilnx-org/kilnx/blob/main/PRINCIPLES.md">Principles</a>
</p>

<br>

```kilnx
model task
  title: text required
  done: bool default false

auth
  table: user
  identity: email
  password: password
  login: /login
  after login: /tasks

page /tasks requires auth
  query tasks: SELECT title, done FROM task
               WHERE owner = :current_user.id
  html
    {{each tasks}}
    <div>{title} {{if done}}✓{{end}}</div>
    {{end}}
```

<br>

### Repositories

| Repo | Description |
|------|-------------|
| [**kilnx**](https://github.com/kilnx-org/kilnx) | Language compiler, runtime, and CLI |
| [**examples**](https://github.com/kilnx-org/examples) | Example applications (CRM, blog, API) |
| [**kilnx-org.github.io**](https://github.com/kilnx-org/kilnx-org.github.io) | Website (kilnx.dev) |
