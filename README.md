# oss-template
[![Build Status](https://img.shields.io/travis/jonathanewerner/oss-template.svg?style=flat-square)](https://travis-ci.org/jonathanewerner/oss-template)
[![Code Coverage](https://img.shields.io/codecov/c/github/jonathanewerner/oss-template.svg?style=flat-square)](https://codecov.io/github/jonathanewerner/oss-template)
![dependencies](https://img.shields.io/david/jonathanewerner/oss-template.svg?style=flat-square)
![devDependencies](https://img.shields.io/david/dev/jonathanewerner/oss-template.svg?style=flat-square)
[![version](https://img.shields.io/npm/v/oss-template.svg?style=flat-square)](http://npm.im/oss-template)
[![downloads](https://img.shields.io/npm/dm/oss-template.svg?style=flat-square)](http://npm-stat.com/charts.html?package=oss-template&from=2015-08-01)
[![MIT License](https://img.shields.io/npm/l/oss-template.svg?style=flat-square)](http://opensource.org/licenses/MIT)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg?style=flat-square)](http://makeapullrequest.com)
[![Commitizen friendly](https://img.shields.io/badge/commitizen-friendly-brightgreen.svg?style=flat-square)](http://commitizen.github.io/cz-cli/)
[![semantic-release](https://img.shields.io/badge/%20%20%F0%9F%93%A6%F0%9F%9A%80-semantic--release-e10079.svg?style=flat-square)](https://github.com/semantic-release/semantic-release)

A template repository for OSS npm packages.

## Usage
```bash
git clone git@github.com:jonathanewerner/oss-template.git <your-new-project-name>
cd <your-new-project-name>
rm -rf .git
npm install
npm run validate # check that skeleton code works
```

Then some manual steps:

1. Change package.json `name`, `description`, `keywords`, `repository`, `author` etc.
2. Create new repo for project on github
3. `git init`
4. `git remote add <your-new-repo-origin>`
5. Adapt badge links to repo name
6. `semantic-release-cli setup`
7. Edit `.travis.yml` by adding / changing to the following:

    ```
    before_install:
      - npm i -g npm@^3.0.0
    script:
      - npm run validate
    after_success:
      - npm run report-coverage && npm run semantic-release
    branches:
      only:
        - master
    ```
8. Change name in line 2 of the LICENCE file.
9. `greenkeeper enable` (`npm install -g greenkeeper && greenkeeper login` if not installed)
