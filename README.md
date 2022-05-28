# Package-Tools

General package tools and config files defaults

> This is part of the [hybrid repro MVC SharePoint example implementation](https://github.com/mauriora/reusable-hybrid-repo-mvc-spfx-examples)

## Table of content

- [Table of content](#table-of-content)
- [Config files defaults](#config-files-defaults)
  - [tsconfig.json](#tsconfigjson)
    - [tsconfig example](#tsconfig-example)
- [Modules](#modules)
  - [loadModules](#loadmodules)
  - [unloadModules](#unloadmodules)
- [Publish](#publish)

## Config files defaults

### tsconfig.json

This package contains a `tsconfig.json` file to be reused in typescript projects to ensure a common configuration. It enables a common upgrade as well.

#### tsconfig example

`tsconfig.json` in your project:

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

## Modules

Add this packge as dependecy of the root workspace and execute the commands there.

(`Un`)`loadModules` scripts work on submodules already part of the root module (workspace).
After (un)loading it will call `yarn install`.

### loadModules

This (down)loads a module already part of the root workspace.

```shell
yarn loadModules .\shared\Package-Tools\
```

or

```shell
yarn loadModules shared/Package-Tools
```

### unloadModules

This empties the working tree of a module already part of the root workspace.

```shell
yarn unloadModules .\shared\Package-Tools\
```

or

```shell
yarn unloadModules shared/Package-Tools
```

## Publish

In this folder execute:

```shell
yarn publish --access public
```
