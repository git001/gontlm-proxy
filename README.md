# gontlm-proxy
:wrench:  NTLM Proxy Forwarder in Golang.

[![GoDoc](https://godoc.org/github.com/bdwyertech/gontlm-proxy?status.svg)](https://godoc.org/github.com/bdwyertech/gontlm-proxy)
[![Build Status](https://travis-ci.org/bdwyertech/gontlm-proxy.svg?branch=dev)](https://travis-ci.org/bdwyertech/gontlm-proxy)
[![Coverage Status](https://coveralls.io/repos/bdwyertech/gontlm-proxy/badge.svg?branch=dev&service=github)](https://coveralls.io/github/bdwyertech/gontlm-proxy?branch=dev)
[![](https://badge.imagelayers.io/bdwyertech/gontlm-proxy:latest.svg)](https://imagelayers.io/?images=bdwyertech/gontlm-proxy:latest)

## Overview
This project was inspired by CNTLM & PX.  Operating behind a corporate proxy can make using tooling difficult.  It can also force you into putting your credentials into ENV variables, definitely not good!  The goal here is to leverage the Windows SSPI subsystem to authenticate to your proxy automatically.

## Usage
When GoNTLM-Proxy first starts, it will create a self-signed certificate, unique to your system.  It is created in your home folder at `~/.gontlm-ca.pem` and `~/.gontlm-ca.key` respectively.  If you want to avoid validation errors, you can add the certificate to your systems trust store.

It reads the configured proxy from the Windows Registry, or can be set via the `GONTLM_PROXY` environment variable.

By default, GoNTLM-Proxy listens locally on port 53128, however this can be set via the `GONTLM_BIND` environment variable.


## Install
Release binaries are available under the GitHub Releases page.  Alternatively, you can do this the Go way.
```console
$ go get github.com/bdwyertech/gontlm-proxy
```

## Development
```console
$ go run .
```

## License

MIT
