# grunt-jsinspect [![NPM version](https://badge.fury.io/js/grunt-jsinspect.png)](http://badge.fury.io/js/grunt-jsinspect)  [![Build Status](true.png)](true)

> Detect copy-pasted and structurally similar code with JSInspect.

## Getting Started
_If you haven't used [grunt][] before, be sure to check out the [Getting Started][] guide._

From the same directory as your project's [Gruntfile][Getting Started] and [package.json][], install this plugin with the following command:

```bash
npm install grunt-jsinspect --save-dev
```

Once that's done, add this line to your project's Gruntfile:

```js
grunt.loadNpmTasks('grunt-jsinspect');
```

If the plugin has been installed correctly, running `grunt --help` at the command line should list the newly-installed plugin's task or tasks. In addition, the plugin should be listed in package.json as a `devDependency`, which ensures that it will be installed whenever the `npm install` command is run.

[grunt]: http://gruntjs.com/
[Getting Started]: https://github.com/gruntjs/grunt/blob/devel/docs/getting_started.md
[package.json]: https://npmjs.org/doc/json.html

## The "jsinspect" task

### Overview
In your project's Gruntfile, add a section named `jsinspect` to the data object passed into `grunt.initConfig()`.

```js
grunt.initConfig({
  jsinspect: {
    options: {
      // Task-specific options go here.
    },
    your_target: {
      // Target-specific file lists and/or options go here.
    },
  },
})
```

### Options

#### options.separator
Type: `String`
Default value: `',  '`

A string value that is used to do something with whatever.

#### options.punctuation
Type: `String`
Default value: `'.'`

A string value that is used to do something else with whatever else.

### Usage Examples

#### Default Options
In this example, the default options are used to do something with whatever. So if the `testing` file has the content `Testing` and the `123` file had the content `1 2 3`, the generated result would be `Testing, 1 2 3.`

```js
grunt.initConfig({
  jsinspect: {
    options: {},
    files: {
      'dest/default_options': ['src/testing', 'src/123'],
    },
  },
})
```

#### Custom Options
In this example, custom options are used to do something else with whatever else. So if the `testing` file has the content `Testing` and the `123` file had the content `1 2 3`, the generated result in this case would be `Testing: 1 2 3 !!!`

```js
grunt.initConfig({
  jsinspect: {
    options: {
      separator: ': ',
      punctuation: ' !!!',
    },
    files: {
      'dest/default_options': ['src/testing', 'src/123'],
    },
  },
})
```

## Contributing
In lieu of a formal styleguide, take care to maintain the existing coding style. Add unit tests for any new or changed functionality. Lint and test your code using [grunt][].


## Release History

 * 2014   v0.1.0   First commit


## License
Copyright (c) 2014 Sebastian Riemschüssel
Licensed under the [MIT license](LICENSE-MIT).

***

Project created by [Sebastian Riemschüssel](https://github.com/riemi-nie).

_This file was generated on Fri Oct 17 2014 10:18:34._
