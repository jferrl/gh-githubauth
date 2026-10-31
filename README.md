# gh-githubauth

A [GitHub CLI](https://cli.github.com) extension that runs
[githubauth](https://github.com/jferrl/go-githubauth): GitHub App JWTs and installation
tokens from your shell, without writing Go.

```bash
gh extension install jferrl/gh-githubauth
```

Run `gh` as your GitHub App rather than as yourself. The token reaches only the command,
is printed nowhere, and is revoked when the command exits:

```bash
gh githubauth token --owner acme --exec -- gh pr list
```

Inside a clone of a repository the App is installed on, nothing else is needed: the token
is for that repository alone.

```bash
gh githubauth token --exec -- gh pr merge 7
```

See the [githubauth README](https://github.com/jferrl/go-githubauth#command-line) for every
flag, the exit codes, and GitHub Enterprise Server.

This repository holds no code. Each release carries the binaries of the
[go-githubauth release](https://github.com/jferrl/go-githubauth/releases) with the same
version, published by its release workflow, starting with v1.12.0. Report issues
[there](https://github.com/jferrl/go-githubauth/issues).
