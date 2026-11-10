# actionlint SDK for Workshop

A development environment for projects that use [actionlint](https://github.com/rhysd/actionlint),
a static checker for GitHub Actions workflow files. It installs the `actionlint`
binary on the workshop PATH so you can lint workflow files inside the workshop.

---

## Reference workshop

A minimal workshop:

```yaml
# workshop.yaml
name: dev
base: ubuntu@24.04
sdks:
  - name: actionlint
    channel: latest/stable
```

This demonstrates a basic setup where `actionlint` is available for linting
GitHub Actions workflow files.

---

## Using the SDK

### Prerequisites, project layout

1. The project repository is mounted at `/project` inside the workshop, as
   with any workshop.
2. Workflow files are located under `.github/workflows/` in the project root.
3. Configuration can optionally be placed at `.github/actionlint.yaml`. See
   the [upstream configuration docs](https://github.com/rhysd/actionlint/blob/main/docs/config.md).

### Run actionlint

Once the workshop is ready:

```bash
workshop exec -- actionlint
```

or, from within the workshop shell:

```bash
workshop shell
actionlint
```

Output is written into the terminal and any reports/artifacts can be saved
into the project directory, which is shared with the host.

---

## Plugs (resources this SDK consumes)

This SDK doesn't define any plugs.

## Slots (resources this SDK provides)

This SDK doesn't define any slots.

---

## Documentation and guidance

- [actionlint official documentation](https://rhysd.github.io/actionlint/)
- [actionlint source repository](https://github.com/rhysd/actionlint)

---

## Community and support

- Workshop community on [Matrix](https://matrix.to/#/#documentation:ubuntu.com)
  and [Discourse](https://discourse.ubuntu.com/)
- Please review our [Code of Conduct](https://ubuntu.com/community/ethos/code-of-conduct)
  before participating.

---

## Contributions

All contributions, including code, documentation updates, and issue reports,
are welcome!

- Open issues or pull requests on the repository you obtained this SDK from.

---

## License and copyright

Copyright 2026 Alex Lowe.

The actionlint SDK is released under the MIT License. The packaged `actionlint` binary is
released under its upstream licenses; see
https://github.com/rhysd/actionlint/blob/main/LICENSE.txt for details.
