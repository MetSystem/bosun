# bosun

Bosun is a time series alerting framework developed by Stack Exchange. Scollector is a metric collection agent. Learn more at [bosun.org](http://bosun.org).

[![Build Status](https://travis-ci.org/bosun-monitor/bosun.svg?branch=master)](https://travis-ci.org/bosun-monitor/bosun/branches)

## building

To build bosun and scollector, clone to `$GOPATH/src/bosun.org`:

```
$ go get bosun.org/cmd/bosun
```

bosun and scollector are found under the `cmd` directory. Run `go build` in the corresponding directories to build each project.

## developing

Install:

* `npm install typescript -g` to be able to compile the ts files to js files.
* `go get github.com/mjibson/esc` to embed the static files. Run `go generate` in `cmd/bosun` when new static assets (like JS and CSS files) are added or changed.

The `w.sh` script will automatically build and run bosun in a loop.
It will update itself when go/js/ts files change, and it runs in read-only mode, not sending any alerts.

```
$ cd cmd/bosun
$ ./w.sh
```

Go Version:
  * We generally upgrade to the latest version Go within a day or two. So consider the correct version of Go always to be the latest stable release.
  
Miniprofiler:
 * Bosun includes [miniprofiler](https://github.com/MiniProfiler/go) in the web UI which can help with debugging. The key combination `ALT-P` will show miniprofiler. This allows you to see timings, as well as the raw queries sent to TSDBs.
 
- elasticSearch
go build -tags="esv5"
