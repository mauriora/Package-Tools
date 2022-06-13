# Package-Tools

General package tools and config files defaults

> This is part of the [hybrid repro MVC SharePoint example implementation](https://github.com/mauriora/reusable-hybrid-repo-mvc-spfx-examples)

## Table of content

- [Table of content](#table-of-content)
- [Config files defaults](#config-files-defaults)
  - [tsconfig.json](#tsconfigjson)
    - [tsconfig example](#tsconfig-example)
  - [releaserc](#releaserc)
- [Publish](#publish)

## Config files defaults

### tsconfig.json

The [tsconfig.json](includes/tsconfig.json) file can be reused in typescript projects to ensure a common configuration. It enables a common upgrade as well.

#### tsconfig example

Add the following `tsconfig.json` to your project folder:

```json
{
  "extends": "@mauriora/package-tools/includes/tsconfig.json",
  "compilerOptions": {
    "outDir": "dist",
    "rootDir": "./src",
    "typeRoots": [
      "./node_modules/@types", "./node_modules/@microsoft"      
    ]
  },
  "include": [
    "src/**/*.ts"
  ]
}
```

### releaserc

The base release config to define common streams for common branches. It is contained in the file [index.js](index.js)

Add the following `.releaserc.json` to your project folder:

```json
{
    "extends": "@mauriora/package-tools"
}
```

in your .env file store the credentials:

```.env
GH_TOKEN=ghp_<...Your.GitHub.key................>
NPM_TOKEN=npm_<..Your.NPM.key....................>
```

in your `package.json` add:

```json
    "scripts": {
        "release": "yarn run dotenv yarn run semantic-release --dry-run",
        "semantic-release": "semantic-release"
    }
```

## Publish

In this folder execute:

```shell
  yarn npm publish --access public
```
