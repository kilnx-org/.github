<p align="center">
  <br>
  <a href="https://kilnx.dev"><img src="https://raw.githubusercontent.com/kilnx-org/kilnx/main/.github/banner.svg" alt="kilnx" width="700"/></a>
  <br>
</p>

<p align="center">
  Declarative backend language that compiles to a single binary.<br>
  28 keywords. Zero framework. SQL is the query language. HTML is the output.
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

### Examples

| App | Description |
|-----|-------------|
| [**kilnx-example-chat**](https://github.com/kilnx-org/kilnx-example-chat) | Minimalist Slack clone in ~650 lines. Channels, threads, DMs, reactions, file uploads, typing indicators, markdown, link unfurl, search, rate limiting. Single .kilnx file, single binary. |
