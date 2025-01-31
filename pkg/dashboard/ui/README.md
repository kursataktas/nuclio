# Contributing

## Setting up for development environment
1. npm install
2. gulp watch --dev

## Setting up for production(staging) environment
1. npm install --production
2. gulp watch --production (gulp watch --staging)

## Watch
Instead of rebuilding the project after every little modification to the source code, `gulp watch` could be used to watch for changes in source code files and automatically re-build.

**Note:** linter will not run in this kind of rebuild, so it is recommended to make a full build from time to time, to make sure linter errors are not piling up.

## Using LiveReload
LiveReload is a tool used by web developers for on-the-fly development and testing.

While running `gulp watch`, it allows you to automatically reload the page on which you're
currently working.

In order to use it, you will first need to install the [LiveReload chrome extension](https://chrome.google.com/webstore/detail/livereload/jnihajbhpnppcggbcgedagnkighmdlei).

After activating the extension, run gulp watch - it now spawns a LiveReload server, which signals your page
to reload every time you make a change in one of your files.

Finally, activate the chrome extension in your tab by clicking on the new LiveReload icon next to the address bar, turning the circle in the middle of it from hollow to opaque.

## Dev flag
Add `--dev` flag to your `gulp` command in order to prevent minification and uglification of source code.  
This way it's easier to debug using the browser's developer tools.

# Demo mode
A regular build results in a dashboard that displays and supports only the parts that were already integrated with the back-end (Iguazio's platform).  
Add `--demo` to your `gulp` command for building the project with **all** of its features enabled.

# Configuration

## Runtime configuration file
If a file named `dashboard-config.json` exists in the root of the web-app (i.e. where also 'index.html' exists), then it is used.  
You can find a sample file in the root of this project.

This file is read on **run-time** and not on build time.  
This means that if you modify it between refreshes, then the changes will take effect.

This file's JSON is merged with the configuration of the web app, so it does not have to consist of _all_ of the available configuration entries.

## Port numbers

Environment variables can be used to override default port numbers:

| Name                    | Description                    | Default value |
|-------------------------|--------------------------------|---------------|
| NCL_PREVIEW_LISTEN_PORT | Preview server for development | 8000          |
| NCL_BACKEND_LISTEN_PORT | Backend server                 | 8070          |
