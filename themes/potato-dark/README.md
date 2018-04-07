# Potato Dark [![license](https://img.shields.io/github/license/mashape/apistatus.svg)](https://github.com/surajmandalcell/potato-dark/blob/master/license.md) 

Potato Dark is a modern, simple and beautiful Hugo theme.

![screenshot](https://github.com/surajmandalcell/potato-dark/blob/master/images/screenshot.png)  

[Full screenshot here](https://github.com/surajmandalcell/potato-dark/blob/master/images/tn.png)

## Overview

* Support for tags
* Responsive design
* Support for Related Content
* Analytics with Google Analytics
* Modern, Simple and beautiful design
* Medium's Image Zoom（[zoom.js](https://github.com/fat/zoom.js/))
* Social links （most social networks available）

Use short code for Image Zoom.

```
{{% zoom-img src="/images/default.jpg" %}}
```

## Installation

cd your hugo site directory and run:

```shell
$ mkdir themes
$ cd themes
$ git clone -b release https://github.com/surajmandalcell/potato-dark
```

Or download it from the release branch

[release](https://github.com/surajmandalcell/potato-dark/tree/release)

## Usage

Use hugo's -t potato-dark or --theme=potato-dark option with hugo commands. Example:

```shell
$ hugo server -t potato-dark -w -D
```

## Configuration

You may specify following options in `config.toml` of your site to make use of
this theme's features.

For getting started with potato dark, copy the [config.toml](https://github.com/surajmandalcell/potato-dark/blob/master/exampleSite/config.toml) file from the exampleSite directory inside Potato's repository to your site repository.

```shell
$ cp themes/potato-dark/exampleSite/config.toml .
```

Now, you can start editing this file and add your own information!

## Contributing

Pull requests, bug fixes and new features are welcome!

Please create feature branches from [develop](https://github.com/surajmandalcell/potato-dark/tree/develop) and submit a PR for any change.

<!-- ## Development

1. Edit the theme or fox somthing
2. Create a pull request and be patient -->

## License

Open sourced under the MIT license.
