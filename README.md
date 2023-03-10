# fluxup
A CLI tool for rendering instances of your Application deployment structure for FluxCD.

<!--ts-->
   * [fluxup](#fluxup)
   * [Features](#features)
   * [Project Layout](#project-layout)
   * [How to use this template](#how-to-use-this-template)
   * [Demo Application](#demo-application)
   * [Makefile Targets](#makefile-targets)
   * [Contribute](#contribute)

<!-- Added by: morelly_t1, at: Tue 10 Aug 2021 08:54:24 AM CEST -->

<!--te-->

[![Test](https://github.com/natrongmbh/fluxup/actions/workflows/test.yml/badge.svg)](https://github.com/natrongmbh/fluxup/actions/workflows/test.yml) [![golangci-lint](https://github.com/natrongmbh/fluxup/actions/workflows/lint.yml/badge.svg)](https://github.com/natrongmbh/fluxup/actions/workflows/lint.yml) [![Go Report Card](https://goreportcard.com/badge/github.com/natrongmbh/fluxup)](https://goreportcard.com/report/github.com/natrongmbh/fluxup) [![Go Reference](https://pkg.go.dev/badge/github.com/natrongmbh/fluxup.svg)](https://pkg.go.dev/github.com/natrongmbh/fluxup) [![codecov](https://codecov.io/gh/natrongmbh/fluxup/branch/main/graph/badge.svg?token=Y5K4SID71F)](https://codecov.io/gh/natrongmbh/fluxup)

Welcome to FluxUp! This powerful command-line interface (CLI) tool is designed to help you manage and understand the deployment structure of your application using FluxCD. With FluxUp, you can easily render clear and concise diagrams that provide insight into how your application is deployed. Whether you're a developer, a devops engineer, or simply someone interested in understanding the inner workings of your application, FluxUp has you covered. So why wait? Try FluxUp today and take control of your application's deployment structure!

# Features

- [goreleaser](https://goreleaser.com/) with `deb.` and `.rpm` package releasing
- [golangci-lint](https://golangci-lint.run/) for linting and formatting
- [Github Actions](.github/worflows) Stages (Lint, Test, Build, Release)
- [Gitlab CI](.gitlab-ci.yml) Configuration (Lint, Test, Build, Release)
- [cobra](https://cobra.dev/) example setup including tests
- [Makefile](Makefile) - with various useful targets and documentation (see Makefile Targets)
- [Github Pages](_config.yml) using [jekyll-theme-minimal](https://github.com/pages-themes/minimal) (checkout [https://natrongmbh.github.io/fluxup/](https://natrongmbh.github.io/fluxup/))
- [pre-commit-hooks](https://pre-commit.com/) for formatting and validating code before committing

# Project Layout

* [assets/](https://pkg.go.dev/github.com/natrongmbh/fluxup/assets) => docs, images, etc
* [cmd/](https://pkg.go.dev/github.com/natrongmbh/fluxup/cmd)  => commandline configurartions (flags, subcommands)
* [pkg/](https://pkg.go.dev/github.com/natrongmbh/fluxup/pkg)  => packages that are okay to import for other projects
* [internal/](https://pkg.go.dev/github.com/natrongmbh/fluxup/pkg)  => packages that are only for project internal purposes
- [`tools/`](tools/) => for automatically shipping all required dependencies when running `go get` (or `make bootstrap`) such as `golang-ci-lint` (see: https://github.com/golang/go/wiki/Modules#how-can-i-track-tool-dependencies-for-a-module)
)

# How to use FluxUp

```sh
bash <(curl -s https://raw.githubusercontent.com/natrongmbh/fluxup/main/install.sh)
```

# Demo Application

```sh
$> fluxup
Usage:
  fluxup [flags]
  fluxup [command]

Available Commands:
  completion  Generate the autocompletion script for the specified shell
  example     example subcommand which adds or multiplies two given integers
  help        Help about any command
  version     Displays binary version

Flags:
  -h, --help   help for fluxup

Use "fluxup [command] --help" for more information about a command.
```

```sh
$> fluxup example 2 5 --add
7

$> fluxup example 2 5 --multiply
10
```

# Makefile Targets

```sh
$> make
bootstrap                      install build deps
build                          build golang binary
clean                          clean up environment
cover                          display test coverage
docker-build                   dockerize golang application
fmt                            format go files
help                           list makefile targets
install                        install golang binary
lint                           lint go files
pre-commit                     run pre-commit hooks
run                            run the app
test                           display test coverage
```

# Contribute

If you find issues in that setup or have some nice features / improvements, I would welcome an issue or a PR :)
