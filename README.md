# SystemJS Config Builder [experimental]
Generate SystemJS config files from node_modules

## [Overview](https://www.youtube.com/watch?v=sqEZeEAbxic)
The easiest way to include modules in SystemJS is *currently* through JSPM. This project aims to provide an alternative, by leveraging the deterministic installs of Yarn (also works with npm) and generating config files to explain to SystemJS how to resolve modules from `node_modules`.

## Progress

- [x] Trace node_modules and build registry
- [x] Generage compatability configs for packages
- [x] Generate valid SystemJS config file
- [x] Make sure loading React.JS works
- [x] Cache registry (to speed up subsequent generations)
- [x] Use own @node polyfills. See [#1](https://github.com/alexisvincent/systemjs-config-builder/issues/1) for progress
- [ ] Allow simple local overrides
- [ ] Use JSPM overrides
- [ ] Fully support npm resolve algorithym (upper node_module and single dep node_modules)
- [ ] Allow dependency filtering (so we don't include deps meant for just the server)
- [ ] Allow configurability
- [ ] Make more robust

Currently, given this [package.json](https://github.com/alexisvincent/systemjs-config-builder/blob/master/test/babel/package.json), 
SystemJS Config Builder generates this [config](https://github.com/alexisvincent/systemjs-config-builder/blob/master/test/babel/generated.config.js).

## Usage
You can test the generation via the cli in [systemjs-tools](https://github.com/alexisvincent/systemjs-tools).

`yarn global add systemjs-tools`

add SystemJS @node browser polyfills

`yarn add systemjs-nodelibs`

and generate the config

`systemjs config`
