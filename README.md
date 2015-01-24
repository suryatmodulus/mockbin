# HTTP Console [![version][npm-version]][npm-url] [![Deploy][docker-image]][docker-url]

[![Build Status][travis-image]][travis-url]
[![Downloads][npm-downloads]][npm-url]
[![Dependencies][david-image]][david-url]
[![Gitter][gitter-image]][gitter-url]
[![License][npm-license]][license-url]


## Table of contents
- [Features](#features) 
- [Installation](#installation) 
- [Usage](#usage) 
- [Documentation](#documentation) 
- [Bugs and feature requests](#bugs-and-feature-requests)
- [Contributing](#contributing)
- [Versioning](#versioning)
- [License](#license)

## Features

- uses HAR format
- supports JSON, YAML, XML, HTML output
- plays nice with proxies (uses the X-Forwarded-* headers for IP resolution)
- allows for HTTP Method Override using the header `X-HTTP-Method-Override` or through query string parameter: `_method`
- create custom bins for experimenting log collection

## Installation

install from source or through [npm](https://www.npmjs.com/):

```shell
npm install httpconsole
```


*read more on [Installation](docs/install.md)*.

### Requirements

other than the dependencies listed in [package.json](package.json) The following are required:

- [Redis](http://redis.io/)

### Configuration

you will need to tell HTTP Console where Redis is:

```shell
npm config set httpconsole:redis redis://127.0.0.1:6379
```

By Default the server will run on port `8080`, you can customize the port like so: 

```shell
npm config set httpconsole:port 8001
```

**note**: in environments such as Heroku, the port which the server is running on, is forwarded to another, by default the application will use the port defined above in all responses (e.g. redirects), if you wish to use a masked port, set the following config:

```shell
npm config set httpconsole:port_mask 80
```

*read more on [Configuration](docs/config.md)*.

### Running

After installing the `npm` package you can now start the server like so:

```shell
npm start
```

## Usage

Once installed, visit [http://localhost:8080/](http://localhost:8080/) to display the web view. *(8080 is [default port](/docs/config.md#port))*

*read more on [Usage](docs/usage.md)*.

## Documentation

Read the full API documentation [here](docs/api.md).

## Bugs and feature requests

Have a bug or a feature request? Please first read the [issue guidelines](CONTRIBUTING.md#using-the-issue-tracker) and search for existing and closed issues. If your problem or idea is not addressed yet, [please open a new issue](/issues).

## Contributing

Please read through our [contributing guidelines](CONTRIBUTING.md). Included are directions for opening issues, coding standards, and notes on development.

More over, if your pull request contains JavaScript patches or features, you must include relevant unit tests.

Editor preferences are available in the [editor config](.editorconfig) for easy use in common text editors. Read more and download plugins at <http://editorconfig.org>.

## Versioning

For transparency into our release cycle and in striving to maintain backward compatibility, this project is maintained under the Semantic Versioning guidelines. Sometimes we screw up, but we'll adhere to these rules whenever possible.

Releases will be numbered with the following format:

`<major>.<minor>.<patch>`

And constructed with the following guidelines:

- Breaking backward compatibility **bumps the major** while resetting minor and patch
- New additions without breaking backward compatibility **bumps the minor** while resetting the patch
- Bug fixes and misc changes **bumps only the patch**

For more information on SemVer, please visit <http://semver.org/>.

## License

Licensed under [The MIT License](LICENSE).

----

Made with &#9829; at [Mashape](https://www.mashape.com/)

[license-url]: https://github.com/ahmadnassri/httpconsole/blob/master/LICENSE

[gitter-url]: https://gitter.im/ahmadnassri/httpconsole
[gitter-image]: https://img.shields.io/badge/Gitter-Join%20Chat-blue.svg?style=flat

[travis-url]: https://travis-ci.org/ahmadnassri/HTTPConsole
[travis-image]: https://img.shields.io/travis/ahmadnassri/httpconsole.svg?style=flat

[npm-url]: https://www.npmjs.com/package/httpconsole
[npm-license]: https://img.shields.io/npm/l/httpconsole.svg?style=flat
[npm-version]: https://badge.fury.io/js/httpconsole.svg
[npm-downloads]: https://img.shields.io/npm/dm/httpconsole.svg?style=flat

[codeclimate-url]: https://codeclimate.com/github/ahmadnassri/httpconsole
[codeclimate-quality]: https://img.shields.io/codeclimate/github/ahmadnassri/httpconsole.svg?style=flat
[codeclimate-coverage]: https://img.shields.io/codeclimate/coverage/github/ahmadnassri/httpconsole.svg?style=flat

[david-url]: https://david-dm.org/ahmadnassri/httpconsole
[david-image]: https://img.shields.io/david/ahmadnassri/httpconsole.svg?style=flat

[docker-image]: https://www.herokucdn.com/deploy/button.svg
[docker-url]: https://heroku.com/deploy?template=https://github.com/ahmadnassri/httpconsole
