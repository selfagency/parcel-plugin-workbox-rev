# parcel-plugin-workbox-rev

An updated plugin for [Parcel][parcel url] to generate a service worker with [Workbox][workbox url], derived from Anders Dahnielson's [parcel-plugin-workbox][ppw url].

## Install

You can either install by running yarn (recommended)

```bash
yarn add parcel-plugin-workbox --dev
```

or use npm

```bash
npm install parcel-plugin-workbox --save-dev
```

## Usage

When you build resources with Parcel, the plugin will generate a service worker `sw.js` and insert it into your project's `index.html` entry file.

You can customize the settings by adding a `workbox` section to your `package.json`.

```
"workbox": {
  importScripts: ['./worker.js'],           // scripts to import into `sw.js`
  globDirectory: './dist',                  // directory to cache (usually output dir)
  globPatterns: [                           // file types to include
  '**/*.{css,html,gif,js,jpg,png,svg,webp}'
}
```

Workbox requires at least one import script to be defined. By default, a `worker.js` file, where you can write the logic for your service worker, will be read from your project's root directory and imported into `sw.js` unless you change this setting. Additionally, a CDN version of Google Workbox is imported automatically.

Note: If you have this plugin active during development, you will need to either disable or manually delete the service worker to bypass caching.

## Versioning

We use [SemVer](http://semver.org/) for versioning. For the versions available, see the [tags on this repository](https://github.com/dahnielson/parcel-plugin-workbox/tags).

## License

This project is licensed under the MIT License - see the LICENSE.md file for details.

[parcel url]: https://parceljs.org
[workbox url]: https://developers.google.com/web/tools/workbox/
[ppw url]: dahnielson/parcel-plugin-workbox
