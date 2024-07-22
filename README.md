# Getting Started With BackStage

## Install node, npx and yarn 

curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.7/install.sh | bash
export NVM_DIR="$HOME/.nvm"

### Install node.js version 18

nvm install 18
node --version #v18.20.4 version displays
npx --version #10.7.0 version displays

### Install yarm
npm install --global yarn

```bash
skhobrag@Sunils-MacBook-Pro backstage % node --version
v18.20.4
skhobrag@Sunils-MacBook-Pro backstage % npx --version
10.7.0
skhobrag@Sunils-MacBook-Pro backstage % yarn --version
1.22.22
skhobrag@Sunils-MacBook-Pro backstage %

```

## Running a Standalone Server Locally
```bash
skhobrag@Sunils-MacBook-Pro backstage % npx @backstage/create-app@latest
Need to install the following packages:
@backstage/create-app@0.5.17
Ok to proceed? (y) y

? Enter a name for the app [required] backstage1

Creating the app...

 Checking if the directory is available:
  checking      backstage1 ✔

 Creating a temporary app directory:

 Preparing files:
  copying       .dockerignore ✔
  copying       .eslintignore ✔
  templating    .eslintrc.js.hbs ✔
  templating    .gitignore.hbs ✔
  copying       .prettierignore ✔
  copying       README.md ✔
  copying       app-config.local.yaml ✔
  copying       app-config.production.yaml ✔
  templating    app-config.yaml.hbs ✔
  templating    backstage.json.hbs ✔
  templating    catalog-info.yaml.hbs ✔
  copying       lerna.json ✔
  templating    package.json.hbs ✔
  copying       playwright.config.ts ✔
  copying       tsconfig.json ✔
  copying       yarn.lock ✔
  copying       README.md ✔
  copying       org.yaml ✔
  copying       entities.yaml ✔
  copying       template.yaml ✔
  copying       catalog-info.yaml ✔
  copying       index.js ✔
  copying       package.json ✔
  copying       README.md ✔
  templating    .eslintrc.js.hbs ✔
  copying       Dockerfile ✔
  copying       README.md ✔
  templating    package.json.hbs ✔
  copying       index.ts ✔
  copying       .eslintignore ✔
  templating    .eslintrc.js.hbs ✔
  templating    package.json.hbs ✔
  copying       app.test.ts ✔
  copying       android-chrome-192x192.png ✔
  copying       favicon-16x16.png ✔
  copying       favicon-32x32.png ✔
  copying       apple-touch-icon.png ✔
  copying       index.html ✔
  copying       favicon.ico ✔
  copying       manifest.json ✔
  copying       robots.txt ✔
  copying       safari-pinned-tab.svg ✔
  copying       App.test.tsx ✔
  copying       App.tsx ✔
  copying       apis.ts ✔
  copying       index.tsx ✔
  copying       setupTests.ts ✔
  copying       LogoFull.tsx ✔
  copying       LogoIcon.tsx ✔
  copying       Root.tsx ✔
  copying       index.ts ✔
  copying       SearchPage.tsx ✔
  copying       EntityPage.tsx ✔

 Moving to final location:
  moving        backstage1 ✔
  fetching      yarn.lock seed ✔

 Installing dependencies:
  determining   yarn version ✔
  executing     yarn install ✔
  executing     yarn tsc ✔

🥇  Successfully created backstage1


 All set! Now you might want to:
  Run the app: cd backstage1 && yarn dev
  Set up the software catalog: https://backstage.io/docs/features/software-catalog/configuration
  Add authentication: https://backstage.io/docs/auth/

skhobrag@Sunils-MacBook-Pro backstage %
```

### A backstage1 directory is created
```bash
skhobrag@Sunils-MacBook-Pro backstage % cd backstage1
skhobrag@Sunils-MacBook-Pro backstage1 %
skhobrag@Sunils-MacBook-Pro backstage1 % yarn dev
```

## Create Tokens for GitHub, Sonarqube and CircleCi

```bash
skhobrag@Sunils-MacBook-Pro backstage % export GITHUB_TOKEN=<YOUR_GITHUB_TOKEN>
skhobrag@Sunils-MacBook-Pro backstage % export SONARCLOUD_TOKEN=<YOUR_SONARCLOUD_TOKEN>
skhobrag@Sunils-MacBook-Pro backstage % export CIRCLECI_TOKEN=<YOUR_CIRCLECI_TOKEN>
```

### Provide Configuration and Install Plugins



## Enable GitHub Integration


```bash
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
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
```

## Enable Sonarqube Integration

```bash
57dba4eea654b5e87ebc08ea297216ae848f2517
```

## Enable CircleCI Integration
```bash
CCIPAT_SjDFpmjQFdGc1fYkmzw5Xi_61d6356ec8899131ad086c6f20a337ce5a7141a7
```

```bash
skhobrag@Sunils-MacBook-Pro backstage % export GITHUB_TOKEN=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
skhobrag@Sunils-MacBook-Pro backstage % export SONARCLOUD_TOKEN=57dba4eea654b5e87ebc08ea297216ae848f2517
skhobrag@Sunils-MacBook-Pro backstage % export CIRCLECI_TOKEN=CCIPAT_SjDFpmjQFdGc1fYkmzw5Xi_61d6356ec8899131ad086c6f20a337ce5a7141a7
skhobrag@Sunils-MacBook-Pro backstage % 

```
