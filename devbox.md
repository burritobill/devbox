<!-- gen-readme start - generated by https://github.com/jetify-com/devbox/ -->

# devbox

Instant, easy, and predictable development environments

## Getting Started

This project uses [devbox](https://github.com/jetify-com/devbox) to manage its
development environment.

Install devbox:

```sh
curl -fsSL https://get.jetify.com/devbox | bash
```

Start the devbox shell:

```sh
devbox shell
```

Run a script in the devbox environment:

```sh
devbox run <script>
```

## Scripts

Scripts are custom commands that can be run using this project's environment.
This project has the following scripts:

- [devbox](#devbox)
  - [Getting Started](#getting-started)
  - [Scripts](#scripts)
  - [Environment](#environment)
  - [Shell Init Hook](#shell-init-hook)
  - [Packages](#packages)
  - [Script Details](#script-details)
    - [devbox run build](#devbox-run-build)
    - [devbox run build-all](#devbox-run-build-all)
    - [devbox run build-darwin-amd64](#devbox-run-build-darwin-amd64)
    - [devbox run build-darwin-arm64](#devbox-run-build-darwin-arm64)
    - [devbox run build-linux-amd64](#devbox-run-build-linux-amd64)
    - [devbox run build-linux-arm64](#devbox-run-build-linux-arm64)
    - [devbox run code](#devbox-run-code)
    - [devbox run fmt](#devbox-run-fmt)
    - [devbox run lint](#devbox-run-lint)
    - [devbox run test](#devbox-run-test)
    - [devbox run tidy](#devbox-run-tidy)
    - [devbox run update-examples](#devbox-run-update-examples)

## Environment

```sh
GOENV="off"
PATH="$PATH:$PWD/dist"
```

## Shell Init Hook

The Shell Init Hook is a script that runs whenever the devbox environment is
instantiated. It runs on `devbox shell` and on `devbox run`.

```sh
test -z $FISH_VERSION && unset CGO_ENABLED GO111MODULE GOARCH GOFLAGS GOMOD GOOS GOROOT GOTOOLCHAIN GOWORK
```

## Packages

- [go@latest](https://www.nixhub.io/packages/go)
- [runx:golangci/golangci-lint@latest](https://www.github.com/golangci/golangci-lint)
- [runx:mvdan/gofumpt@latest](https://www.github.com/mvdan/gofumpt)

## Script Details

### devbox run build

Build devbox for the current platform

```sh
go build -o dist/devbox ./cmd/devbox
```

&ensp;

### devbox run build-all

```sh
devbox run build-darwin-amd64
devbox run build-darwin-arm64
devbox run build-linux-amd64
devbox run build-linux-arm64
```

&ensp;

### devbox run build-darwin-amd64

```sh
GOOS=darwin GOARCH=amd64 go build -o dist/devbox-darwin-amd64 ./cmd/devbox
```

&ensp;

### devbox run build-darwin-arm64

```sh
GOOS=darwin GOARCH=arm64 go build -o dist/devbox-darwin-arm64 ./cmd/devbox
```

&ensp;

### devbox run build-linux-amd64

```sh
GOOS=linux GOARCH=amd64 go build -o dist/devbox-linux-amd64 ./cmd/devbox
```

&ensp;

### devbox run build-linux-arm64

```sh
GOOS=linux GOARCH=arm64 go build -o dist/devbox-linux-arm64 ./cmd/devbox
```

&ensp;

### devbox run code

Open VSCode

```sh
code .
```

&ensp;

### devbox run fmt

```sh
scripts/gofumpt.sh
```

&ensp;

### devbox run lint

```sh
golangci-lint run --timeout 5m && scripts/gofumpt.sh
```

&ensp;

### devbox run test

```sh
go test -race -cover ./...
```

&ensp;

### devbox run tidy

```sh
go mod tidy
```

&ensp;

### devbox run update-examples

```sh
devbox run build && go run testscripts/testrunner/updater/main.go
```

&ensp;

<!-- gen-readme end -->
