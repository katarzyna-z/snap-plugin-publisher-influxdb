[![Build Status](https://travis-ci.org/intelsdi-x/snap-plugin-publisher-influxdb.svg?branch=master)](https://travis-ci.org/intelsdi-x/snap-plugin-publisher-influxdb)

# Snap publisher plugin - InfluxDB 

This plugin supports pushing metrics into an InfluxDB instance.

It's used in the [Snap framework](http://github.com/intelsdi-x/snap).

1. [Getting Started](#getting-started)
  * [System Requirements](#system-requirements)
  * [Installation](#installation)
  * [Configuration and Usage](#configuration-and-usage)
2. [Documentation](#documentation)
  * [Collected Metrics](#collected-metrics)
  * [Examples](#examples)
  * [Roadmap](#roadmap)
3. [Community Support](#community-support)
4. [Contributing](#contributing)
5. [License](#license)
6. [Acknowledgements](#acknowledgements)

## Getting Started

### System Requirements

* [golang 1.6+](https://golang.org/dl/) (needed only for building)

Support Matrix

- InfluxDB Plugin: v2 -> InfluxDB Version 0.9.1 -> Snap version 0.2.0
- InfluxDB Plugin: v3 -> InfluxDB Version >= 0.9.1 -> Snap version 0.2.0
- InfluxDB Plugin: v4 -> InfluxDB Version >= 0.9.1 -> Snap version 0.3.x
- InfluxDB Plugin: v6 -> InfluxDB Version >= 0.9.1 -> Snap version 0.8.0-beta
- InfluxDB Plugin: v7 -> InfluxDB Version >= 0.9.1 -> Snap version 0.8.0-beta-114 and greater
- InfluxDB Plugin: v12 -> InfluxDB Version >= 0.9.3 -> Snap version 0.8.0-beta-114 and greater
- InfluxDB Plugin: v12 -> InfluxDB Version >= 0.9.4 -> Snap version 0.13.0-beta and greater

### Known Limitation

* InfluxDB (tested with InfluxDB 0.10.0) does not support uint64 as type of data. Metrics with uint64 type are converted to int64 by Snap publisher plugin. uint64 values higher than maximum int64 value are converted to negative value and saved in InfluxDB. Overflow cases are logged.

### Installation

#### Download InfluxDB plugin binary:
You can get the pre-built binaries for your OS and architecture at plugin's [GitHub Releases](https://github.com/intelsdi-x/snap-plugin-publisher-influxdb/releases) page.

#### To build the plugin binary:
Fork https://github.com/intelsdi-x/snap-plugin-publisher-influxdb

Clone repo into `$GOPATH/src/github.com/intelsdi-x/`:

```
$ git clone https://github.com/<yourGithubID>/snap-plugin-publisher-influxdb.git
```

Build the plugin by running make within the cloned repo:
```
$ make
```
This builds the plugin in `./build`

### Configuration and Usage
* Set up the [Snap framework](https://github.com/intelsdi-x/snap/blob/master/README.md#getting-started)

## Documentation

The plugin expects you to provide the following parameters:
 - `host`
 - `port`
 - `database`
 - `user`
 - `password`

You can also set the following options if needed:
 - `https` defaults to `false` (boolean). Set to true to connect to InfluxDB via HTTPS.
 - `skip-verify` defaults to `false` (boolean). Set to true to complain if the certificate used is not issued by a trusted CA.

### Examples

See [examples/tasks](https://github.com/intelsdi-x/snap-plugin-publisher-influxdb/tree/master/examples/tasks) folder for examples


### Roadmap

There isn't a current roadmap for this plugin, but it is in active development. As we launch this plugin, we do not have any outstanding requirements for the next release.

If you have a feature request, please add it as an [issue](https://github.com/intelsdi-x/snap-plugin-publisher-influxdb/issues/new) and/or submit a [pull request](https://github.com/intelsdi-x/snap-plugin-publisher-influxdb/pulls).

## Community Support
This repository is one of **many** plugins in **Snap**, a powerful telemetry framework. See the full project at http://github.com/intelsdi-x/snap To reach out to other users, head to the [main framework](https://github.com/intelsdi-x/snap#community-support)

## Contributing
We love contributions! 

There's more than one way to give back, from examples to blogs to code updates. See our recommended process in [CONTRIBUTING.md](CONTRIBUTING.md).

## License
[Snap](http://github.com/intelsdi-x/snap), along with this plugin, is an Open Source software released under the Apache 2.0 [License](LICENSE).

## Acknowledgements
* Author: [Justin Guidroz](https://github.com/geauxvirtual)
* Author: [Joel Cooklin](https://github.com/jcooklin)

And **thank you!** Your contribution, through code and participation, is incredibly important to us.
