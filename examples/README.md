# Optional GitHub Actions validation

[github-actions-validate.yml](github-actions-validate.yml) runs the existing
standard-library package validator on pushes, pull requests, and manual runs.
It uses Python 3.12, grants only `contents: read`, and pins actions to specific
commits.

To enable it, a repository maintainer can copy the template to
`.github/workflows/validate.yml` and commit it with a credential permitted to
write workflow files. Merely adding this example does not activate GitHub Actions.

Run the same validation locally with:

```sh
python scripts/validate.py
```

The validator checks package links, skill metadata, license hashes, and explicit
preservation conditions in reference fixtures. It does not invoke an LLM or
measure editing quality. Behavioral evaluation uses [the case criteria](../evals/cases.json)
in the target client.
