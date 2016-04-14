# node-package-template

A template repository for OSS npm packages. Forked from [jonathanewerner/oss-template](https://github.com/jonathanewerner/oss-template), not supposed to be published to npm :)

## Usage
```bash
git clone git@github.com:jonathanewerner/node-package-template.git <your-new-project-name>
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
