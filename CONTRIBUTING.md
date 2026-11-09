# Contributing

Thank you for considering a contribution to this project.

## Before contributing

- Open an issue before submitting a significant change.
- Describe the problem, the environment tested and the expected result.
- Do not include credentials, passwords, private IP addresses, tokens,
  or sensitive logs in issues, pull requests or examples.

## Scope

This project automates the installation and initial configuration of
Nagios Core 4.5.14 on CentOS 7.

Changes should remain focused on:

- CentOS 7 compatibility.
- Reliable installation and configuration.
- Clear documentation.
- Security and safe execution.
- Reproducible deployment steps.

## Before submitting a pull request

1. Fork or create a branch.
2. Make small, focused changes.
3. Update `README.md` and files in `docs/` when behavior changes.
4. Run:

```bash
bash -n nagios_automatizado.sh
shellcheck nagios_automatizado.sh
```

5. Test the change in a disposable CentOS 7 virtual machine.
6. Describe what changed, why it changed and how it was tested.

## Pull request checklist

- [ ] The change is compatible with CentOS 7.
- [ ] The script syntax was validated.
- [ ] ShellCheck was run, when available.
- [ ] Documentation was updated.
- [ ] No credentials or sensitive data were added.
- [ ] Security implications were considered.
- [ ] The change was tested in an isolated environment.

## Reporting problems

Open an issue with:

- CentOS 7 version and architecture.
- Nagios Core version.
- Exact command executed.
- Full error output, with sensitive data removed.
- Steps already attempted.
- Expected and actual result.
