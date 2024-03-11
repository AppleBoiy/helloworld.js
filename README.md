# helloworld.js

a hello world program written in javascript

## Introduction

The goal of this project is to create a `homebrew` formula from JavaScript.

### Project Structure

```bash
.
├── index.js # entry point of the package
├── package.json
├── dist
│   ├── # compiled files
│   └── # .tar.gz file
└── build
    └── index.js # converted file from package into single js file 
```

## Prerequisites

### Required Tools

- [Node.js](https://nodejs.org/en/) v18 is recommended (v20 not compatible with `pkg` officially)
- `ncc` is a simple CLI for compiling a Node.js module into a single file, together with all its dependencies, gcc-style.
  - `npm install -g @vercel/ncc` is required to compile the package into single file for `pkg` to work
- `pkg` is a command line tool for creating executables from Node.js programs
  - `npm install -g @vercel/pkg` is required to create a standalone executable file from the package
  - for node v20, use `npm install -g @yao-pkg/pkg` instead

### Instructions
  
1. create package's repository on GitHub

create a new repository on GitHub or using `git init` command to create a new repository locally.
```bash
$ git init
$ git add .
$ git commit -m "Initial commit"
$ git remote add origin <url>
$ git push -u origin master
```

or create a new github repository from `gh` command line tool

```bash
$ gh repo create helloworld.js
```

2. create a `package.json` file

```bash
$ npm init -y
```

3. create a `index.js` file

Write a simple hello world program in `index.js` file.

```javascript
console.log('Hello, World!');
```

4. create compiled script

```bash
$ npm run build && npm run package
```

5. create `tar.gz` file for release

```bash
$ mkdir dist # if not exists
$ npm run tar
```

6. create a release on GitHub

```bash
$ gh release create <tag> dist/<tar.gz file>
```

## Release via Homebrew Formula

please visit [Homebrew](https://brew.sh) for more information on how to create a formula for your package.

---

Need assistance? Check out my [discussion board](https://github.com/AppleBoiy/cs-wiki101/discussions) or review the [GitHub status page](https://www.githubstatus.com).

&copy; 2023 AppleBoiy &bull; [Code of Conduct](https://www.contributor-covenant.org/version/2/1/code_of_conduct/code_of_conduct.md) &bull; [MIT License](LICENSE)