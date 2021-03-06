# Rump Server
[![NPM](http://img.shields.io/npm/v/rump-server.svg?style=flat-square)](https://www.npmjs.org/package/rump-server)
![License](http://img.shields.io/npm/l/rump-server.svg?style=flat-square)
[![Dependencies](http://img.shields.io/david/rumps/rump-server.svg?style=flat-square)](https://david-dm.org/rumps/rump-server)


## About
Rump Server is a Rump module that starts up a local server that serves built
assets using [pushserve](https://github.com/paulmillr/pushserve). For more
information, visit the [Rump repository](https://github.com/rumps/rump).


## API
The following is appended to the core Rump API:

### `rump.addGulpTasks(options)`
This module adds the following tasks:

- `server` will start up the `watch` task, then start up BrowserSync on the
destination path.
- `server:prod` is the same as `server` with `options.environment` set to
`'production'` for a production build.
- `info:server` will display information on what this specific module does,
specifically the port number the local server is started at. This task is also
added to the `info` task.

### `rump.configure(options)`
Redefine options for Rump and Rump modules to follow. In addition to what
options Rump and other Rump modules offer, the following options are
available alongside default values:

#### `options.server.port` (`process.env.PORT` or `3000`)
This specifies which port to run pushserve under.

#### `options.server.pushserve`
This specifies any options you want to override in pushserve. Visit the
[project page](https://github.com/paulmillr/pushserve) for specific options
available.

### `rump.configs.pushserve`
This contains the generated options that are passed to pushserve in the Gulp
task. This is a good way to see what options are generated based on defaults
and overrides.
