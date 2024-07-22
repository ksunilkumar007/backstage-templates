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

```bash
skhobrag@Sunils-MacBook-Pro backstage % export GITHUB_TOKEN=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
skhobrag@Sunils-MacBook-Pro backstage % export SONARCLOUD_TOKEN=57dba4eea654b5e87ebc08ea297216ae848f2517
skhobrag@Sunils-MacBook-Pro backstage % export CIRCLECI_TOKEN=CCIPAT_SjDFpmjQFdGc1fYkmzw5Xi_61d6356ec8899131ad086c6f20a337ce5a7141a7
skhobrag@Sunils-MacBook-Pro backstage % 

```
Edit the file "app-config.yaml" and add the token GITHUB_TOKEN,SONARCLOUD_TOKEN and CIRCLECI_TOKEN


## Enable GitHub Integration

```bash
skhobrag@Sunils-MacBook-Pro backstage1 %  yarn --cwd packages/backend add @backstage/plugin-scaffolder-backend-module-github 
yarn add v1.22.22
[1/4] 🔍  Resolving packages...
warning Lockfile has incorrect entry for "@types/react@^16.13.1 || ^17.0.0". Ignoring it.
[2/4] 🚚  Fetching packages...
warning Pattern ["app@link:packages/app"] is trying to unpack in the same destination "/Users/skhobrag/Library/Caches/Yarn/v6/npm-app-0.0.0/node_modules/app" as pattern ["app@0.0.0"]. This could result in non-deterministic behavior, skipping.
[3/4] 🔗  Linking dependencies...
warning "workspace-aggregator-ba00996d-dfee-440c-913f-fd4ae5a0f398 > app > @backstage/theme@0.5.6" has unmet peer dependency "@types/react@^16.13.1 || ^17.0.0 || ^18.0.0".
warning "workspace-aggregator-ba00996d-dfee-440c-913f-fd4ae5a0f398 > app > @material-ui/core@4.12.4" has incorrect peer dependency "react@^16.8.0 || ^17.0.0".
warning "workspace-aggregator-ba00996d-dfee-440c-913f-fd4ae5a0f398 > app > @material-ui/core@4.12.4" has incorrect peer dependency "react-dom@^16.8.0 || ^17.0.0".
warning "workspace-aggregator-ba00996d-dfee-440c-913f-fd4ae5a0f398 > app > @material-ui/icons@4.11.3" has incorrect peer dependency "react@^16.8.0 || ^17.0.0".
warning "workspace-aggregator-ba00996d-dfee-440c-913f-fd4ae5a0f398 > app > @material-ui/icons@4.11.3" has incorrect peer dependency "react-dom@^16.8.0 || ^17.0.0".
warning "workspace-aggregator-ba00996d-dfee-440c-913f-fd4ae5a0f398 > app > @backstage/test-utils@1.5.8" has incorrect peer dependency "@testing-library/react@^15.0.0".
warning "workspace-aggregator-ba00996d-dfee-440c-913f-fd4ae5a0f398 > app > @backstage/core-components > @material-ui/lab@4.0.0-alpha.61" has incorrect peer dependency "react@^16.8.0 || ^17.0.0".
warning "workspace-aggregator-ba00996d-dfee-440c-913f-fd4ae5a0f398 > app > @backstage/core-components > @material-ui/lab@4.0.0-alpha.61" has incorrect peer dependency "react-dom@^16.8.0 || ^17.0.0".
warning "workspace-aggregator-ba00996d-dfee-440c-913f-fd4ae5a0f398 > app > @backstage/plugin-catalog-react > material-ui-popup-state@1.9.3" has incorrect peer dependency "react@^15.0.0 || ^16.0.0 || ^17.0.0".
warning "workspace-aggregator-ba00996d-dfee-440c-913f-fd4ae5a0f398 > app > @backstage/plugin-scaffolder > @uiw/react-codemirror@4.23.0" has unmet peer dependency "@babel/runtime@>=7.11.0".
warning "workspace-aggregator-ba00996d-dfee-440c-913f-fd4ae5a0f398 > app > @backstage/plugin-scaffolder > @uiw/react-codemirror@4.23.0" has unmet peer dependency "@codemirror/state@>=6.0.0".
warning "workspace-aggregator-ba00996d-dfee-440c-913f-fd4ae5a0f398 > app > @backstage/plugin-scaffolder > @uiw/react-codemirror@4.23.0" has unmet peer dependency "@codemirror/theme-one-dark@>=6.0.0".
warning "workspace-aggregator-ba00996d-dfee-440c-913f-fd4ae5a0f398 > app > @backstage/plugin-scaffolder > @uiw/react-codemirror@4.23.0" has unmet peer dependency "codemirror@>=6.0.0".
warning "workspace-aggregator-ba00996d-dfee-440c-913f-fd4ae5a0f398 > app > @backstage/plugin-techdocs > @material-ui/styles@4.11.5" has incorrect peer dependency "react@^16.8.0 || ^17.0.0".
warning "workspace-aggregator-ba00996d-dfee-440c-913f-fd4ae5a0f398 > app > @backstage/plugin-techdocs > @material-ui/styles@4.11.5" has incorrect peer dependency "react-dom@^16.8.0 || ^17.0.0".
warning "workspace-aggregator-ba00996d-dfee-440c-913f-fd4ae5a0f398 > app > @backstage/plugin-user-settings > @backstage/plugin-signals-react@0.0.4" has incorrect peer dependency "react@^16.13.1 || ^17.0.0".
warning "workspace-aggregator-ba00996d-dfee-440c-913f-fd4ae5a0f398 > app > @material-ui/core > @material-ui/system@4.12.2" has incorrect peer dependency "react@^16.8.0 || ^17.0.0".
warning "workspace-aggregator-ba00996d-dfee-440c-913f-fd4ae5a0f398 > app > @material-ui/core > @material-ui/system@4.12.2" has incorrect peer dependency "react-dom@^16.8.0 || ^17.0.0".
warning "workspace-aggregator-ba00996d-dfee-440c-913f-fd4ae5a0f398 > app > @material-ui/core > @material-ui/utils@4.11.3" has incorrect peer dependency "react@^16.8.0 || ^17.0.0".
warning "workspace-aggregator-ba00996d-dfee-440c-913f-fd4ae5a0f398 > app > @material-ui/core > @material-ui/utils@4.11.3" has incorrect peer dependency "react-dom@^16.8.0 || ^17.0.0".
warning "workspace-aggregator-ba00996d-dfee-440c-913f-fd4ae5a0f398 > app > @backstage/core-components > @material-table/core > @material-ui/pickers@3.3.11" has incorrect peer dependency "react@^16.8.0 || ^17.0.0".
warning "workspace-aggregator-ba00996d-dfee-440c-913f-fd4ae5a0f398 > app > @backstage/core-components > @material-table/core > @material-ui/pickers@3.3.11" has incorrect peer dependency "react-dom@^16.8.0 || ^17.0.0".
warning "workspace-aggregator-ba00996d-dfee-440c-913f-fd4ae5a0f398 > app > @backstage/plugin-api-docs > @graphiql/react > codemirror-graphql@2.0.12" has unmet peer dependency "@codemirror/language@6.0.0".
warning "workspace-aggregator-ba00996d-dfee-440c-913f-fd4ae5a0f398 > app > @backstage/plugin-scaffolder > @backstage/plugin-scaffolder-react > use-immer@0.9.0" has unmet peer dependency "immer@>=2.0.0".
warning "workspace-aggregator-ba00996d-dfee-440c-913f-fd4ae5a0f398 > app > @backstage/plugin-scaffolder > @uiw/react-codemirror > @uiw/codemirror-extensions-basic-setup@4.23.0" has unmet peer dependency "@codemirror/autocomplete@>=6.0.0".
warning "workspace-aggregator-ba00996d-dfee-440c-913f-fd4ae5a0f398 > app > @backstage/plugin-scaffolder > @uiw/react-codemirror > @uiw/codemirror-extensions-basic-setup@4.23.0" has unmet peer dependency "@codemirror/lint@>=6.0.0".
warning "workspace-aggregator-ba00996d-dfee-440c-913f-fd4ae5a0f398 > app > @backstage/plugin-scaffolder > @uiw/react-codemirror > @uiw/codemirror-extensions-basic-setup@4.23.0" has unmet peer dependency "@codemirror/search@>=6.0.0".
warning "workspace-aggregator-ba00996d-dfee-440c-913f-fd4ae5a0f398 > backend > @backstage/plugin-search-backend-module-techdocs > @backstage/plugin-techdocs-node > @aws-sdk/lib-storage@3.616.0" has incorrect peer dependency "@aws-sdk/client-s3@^3.616.0".
warning "workspace-aggregator-ba00996d-dfee-440c-913f-fd4ae5a0f398 > app > @backstage/plugin-api-docs > swagger-ui-react > swagger-client > ramda-adjunct@5.0.1" has unmet peer dependency "ramda@>= 0.30.0".
warning "workspace-aggregator-ba00996d-dfee-440c-913f-fd4ae5a0f398 > app > @backstage/plugin-scaffolder > @uiw/react-codemirror > @uiw/codemirror-extensions-basic-setup > @codemirror/autocomplete@6.17.0" has unmet peer dependency "@lezer/common@^1.0.0".
warning "workspace-aggregator-ba00996d-dfee-440c-913f-fd4ae5a0f398 > backend > @backstage/backend-common > @aws-sdk/credential-providers > @aws-sdk/credential-provider-sso > @aws-sdk/token-providers@3.614.0" has unmet peer dependency "@aws-sdk/client-sso-oidc@^3.614.0".
[4/4] 🔨  Building fresh packages...
success Saved lockfile.
success Saved 3 new dependencies.
info Direct dependencies
info All dependencies
├─ @backstage/plugin-scaffolder-backend-module-github@0.4.0
├─ @types/scheduler@0.16.8
└─ app@0.0.0
✨  Done in 15.02s.
skhobrag@Sunils-MacBook-Pro backstage1 % 

```
Add the line below line to the file backstage1/packages/backend/src/index.ts
 backend.add(import('@backstage/plugin-scaffolder-backend-module-github'));

## Enable Sonarqube Integration

```bash
skhobrag@Sunils-MacBook-Pro backstage1 %  yarn --cwd packages/app add @backstage-community/plugin-sonarqube 
yarn add v1.22.22
[1/4] 🔍  Resolving packages...
[2/4] 🚚  Fetching packages...
warning Pattern ["app@link:packages/app"] is trying to unpack in the same destination "/Users/skhobrag/Library/Caches/Yarn/v6/npm-app-0.0.0/node_modules/app" as pattern ["app@0.0.0","app@0.0.0"]. This could result in non-deterministic behavior, skipping.
[3/4] 🔗  Linking dependencies...
warning "@backstage-community/plugin-sonarqube > @backstage/core-components@0.14.9" has unmet peer dependency "react@^16.13.1 || ^17.0.0 || ^18.0.0".
warning "@backstage-community/plugin-sonarqube > @backstage/core-components@0.14.9" has unmet peer dependency "react-dom@^16.13.1 || ^17.0.0 || ^18.0.0".
warning "@backstage-community/plugin-sonarqube > @backstage/core-components@0.14.9" has unmet peer dependency "react-router-dom@6.0.0-beta.0 || ^6.3.0".
warning "@backstage-community/plugin-sonarqube > @backstage/core-plugin-api@1.9.3" has unmet peer dependency "react@^16.13.1 || ^17.0.0 || ^18.0.0".
warning "@backstage-community/plugin-sonarqube > @backstage/core-plugin-api@1.9.3" has unmet peer dependency "react-dom@^16.13.1 || ^17.0.0 || ^18.0.0".
warning "@backstage-community/plugin-sonarqube > @backstage/core-plugin-api@1.9.3" has unmet peer dependency "react-router-dom@6.0.0-beta.0 || ^6.3.0".
warning "@backstage-community/plugin-sonarqube > @backstage/plugin-catalog-react@1.12.2" has unmet peer dependency "react@^16.13.1 || ^17.0.0 || ^18.0.0".
warning "@backstage-community/plugin-sonarqube > @backstage/plugin-catalog-react@1.12.2" has unmet peer dependency "react-dom@^16.13.1 || ^17.0.0 || ^18.0.0".
warning "@backstage-community/plugin-sonarqube > @backstage/plugin-catalog-react@1.12.2" has unmet peer dependency "react-router-dom@6.0.0-beta.0 || ^6.3.0".
warning "workspace-aggregator-cff61f0c-570b-4055-ac78-68b074dc3fa6 > app > @backstage/theme@0.5.6" has unmet peer dependency "@types/react@^16.13.1 || ^17.0.0 || ^18.0.0".
warning "@backstage-community/plugin-sonarqube > @material-ui/core@4.12.4" has unmet peer dependency "react@^16.8.0 || ^17.0.0".
warning "@backstage-community/plugin-sonarqube > @material-ui/core@4.12.4" has unmet peer dependency "react-dom@^16.8.0 || ^17.0.0".
warning "@backstage-community/plugin-sonarqube > @material-ui/icons@4.11.3" has unmet peer dependency "react@^16.8.0 || ^17.0.0".
warning "@backstage-community/plugin-sonarqube > @material-ui/icons@4.11.3" has unmet peer dependency "react-dom@^16.8.0 || ^17.0.0".
warning "@backstage-community/plugin-sonarqube > react-use@17.5.1" has unmet peer dependency "react@*".
warning "@backstage-community/plugin-sonarqube > react-use@17.5.1" has unmet peer dependency "react-dom@*".
warning "workspace-aggregator-cff61f0c-570b-4055-ac78-68b074dc3fa6 > app > @backstage/test-utils@1.5.8" has incorrect peer dependency "@testing-library/react@^15.0.0".
warning "workspace-aggregator-cff61f0c-570b-4055-ac78-68b074dc3fa6 > app > @backstage/core-components > @material-ui/lab@4.0.0-alpha.61" has incorrect peer dependency "react@^16.8.0 || ^17.0.0".
warning "workspace-aggregator-cff61f0c-570b-4055-ac78-68b074dc3fa6 > app > @backstage/core-components > @material-ui/lab@4.0.0-alpha.61" has incorrect peer dependency "react-dom@^16.8.0 || ^17.0.0".
warning "workspace-aggregator-cff61f0c-570b-4055-ac78-68b074dc3fa6 > app > @backstage/plugin-catalog-react > material-ui-popup-state@1.9.3" has incorrect peer dependency "react@^15.0.0 || ^16.0.0 || ^17.0.0".
warning "workspace-aggregator-cff61f0c-570b-4055-ac78-68b074dc3fa6 > app > @backstage/plugin-scaffolder > @uiw/react-codemirror@4.23.0" has unmet peer dependency "@babel/runtime@>=7.11.0".
warning "workspace-aggregator-cff61f0c-570b-4055-ac78-68b074dc3fa6 > app > @backstage/plugin-scaffolder > @uiw/react-codemirror@4.23.0" has unmet peer dependency "@codemirror/state@>=6.0.0".
warning "workspace-aggregator-cff61f0c-570b-4055-ac78-68b074dc3fa6 > app > @backstage/plugin-scaffolder > @uiw/react-codemirror@4.23.0" has unmet peer dependency "@codemirror/theme-one-dark@>=6.0.0".
warning "workspace-aggregator-cff61f0c-570b-4055-ac78-68b074dc3fa6 > app > @backstage/plugin-scaffolder > @uiw/react-codemirror@4.23.0" has unmet peer dependency "codemirror@>=6.0.0".
warning "@backstage-community/plugin-sonarqube > @material-ui/styles@4.11.5" has unmet peer dependency "react@^16.8.0 || ^17.0.0".
warning "@backstage-community/plugin-sonarqube > @material-ui/styles@4.11.5" has unmet peer dependency "react-dom@^16.8.0 || ^17.0.0".
warning "workspace-aggregator-cff61f0c-570b-4055-ac78-68b074dc3fa6 > app > @backstage/plugin-user-settings > @backstage/plugin-signals-react@0.0.4" has incorrect peer dependency "react@^16.13.1 || ^17.0.0".
warning "workspace-aggregator-cff61f0c-570b-4055-ac78-68b074dc3fa6 > app > @material-ui/core > @material-ui/system@4.12.2" has incorrect peer dependency "react@^16.8.0 || ^17.0.0".
warning "workspace-aggregator-cff61f0c-570b-4055-ac78-68b074dc3fa6 > app > @material-ui/core > @material-ui/system@4.12.2" has incorrect peer dependency "react-dom@^16.8.0 || ^17.0.0".
warning "workspace-aggregator-cff61f0c-570b-4055-ac78-68b074dc3fa6 > app > @material-ui/core > @material-ui/utils@4.11.3" has incorrect peer dependency "react@^16.8.0 || ^17.0.0".
warning "workspace-aggregator-cff61f0c-570b-4055-ac78-68b074dc3fa6 > app > @material-ui/core > @material-ui/utils@4.11.3" has incorrect peer dependency "react-dom@^16.8.0 || ^17.0.0".
warning "workspace-aggregator-cff61f0c-570b-4055-ac78-68b074dc3fa6 > app > @backstage/core-components > @material-table/core > @material-ui/pickers@3.3.11" has incorrect peer dependency "react@^16.8.0 || ^17.0.0".
warning "workspace-aggregator-cff61f0c-570b-4055-ac78-68b074dc3fa6 > app > @backstage/core-components > @material-table/core > @material-ui/pickers@3.3.11" has incorrect peer dependency "react-dom@^16.8.0 || ^17.0.0".
warning "@backstage-community/plugin-sonarqube > rc-progress > rc-util@5.43.0" has unmet peer dependency "react@>=16.9.0".
warning "@backstage-community/plugin-sonarqube > rc-progress > rc-util@5.43.0" has unmet peer dependency "react-dom@>=16.9.0".
warning "workspace-aggregator-cff61f0c-570b-4055-ac78-68b074dc3fa6 > app > @backstage/plugin-api-docs > @graphiql/react > codemirror-graphql@2.0.12" has unmet peer dependency "@codemirror/language@6.0.0".
warning "workspace-aggregator-cff61f0c-570b-4055-ac78-68b074dc3fa6 > app > @backstage/plugin-scaffolder > @backstage/plugin-scaffolder-react > use-immer@0.9.0" has unmet peer dependency "immer@>=2.0.0".
warning "workspace-aggregator-cff61f0c-570b-4055-ac78-68b074dc3fa6 > app > @backstage/plugin-scaffolder > @uiw/react-codemirror > @uiw/codemirror-extensions-basic-setup@4.23.0" has unmet peer dependency "@codemirror/autocomplete@>=6.0.0".
warning "workspace-aggregator-cff61f0c-570b-4055-ac78-68b074dc3fa6 > app > @backstage/plugin-scaffolder > @uiw/react-codemirror > @uiw/codemirror-extensions-basic-setup@4.23.0" has unmet peer dependency "@codemirror/lint@>=6.0.0".
warning "workspace-aggregator-cff61f0c-570b-4055-ac78-68b074dc3fa6 > app > @backstage/plugin-scaffolder > @uiw/react-codemirror > @uiw/codemirror-extensions-basic-setup@4.23.0" has unmet peer dependency "@codemirror/search@>=6.0.0".
warning "workspace-aggregator-cff61f0c-570b-4055-ac78-68b074dc3fa6 > backend > @backstage/plugin-search-backend-module-techdocs > @backstage/plugin-techdocs-node > @aws-sdk/lib-storage@3.616.0" has incorrect peer dependency "@aws-sdk/client-s3@^3.616.0".
warning "workspace-aggregator-cff61f0c-570b-4055-ac78-68b074dc3fa6 > app > @backstage/plugin-api-docs > swagger-ui-react > swagger-client > ramda-adjunct@5.0.1" has unmet peer dependency "ramda@>= 0.30.0".
warning "workspace-aggregator-cff61f0c-570b-4055-ac78-68b074dc3fa6 > app > @backstage/plugin-scaffolder > @uiw/react-codemirror > @uiw/codemirror-extensions-basic-setup > @codemirror/autocomplete@6.17.0" has unmet peer dependency "@lezer/common@^1.0.0".
warning "workspace-aggregator-cff61f0c-570b-4055-ac78-68b074dc3fa6 > backend > @backstage/backend-common > @aws-sdk/credential-providers > @aws-sdk/credential-provider-sso > @aws-sdk/token-providers@3.614.0" has unmet peer dependency "@aws-sdk/client-sso-oidc@^3.614.0".
warning "@backstage-community/plugin-sonarqube > rc-progress@4.0.0" has unmet peer dependency "react@>=16.9.0".
warning "@backstage-community/plugin-sonarqube > rc-progress@4.0.0" has unmet peer dependency "react-dom@>=16.9.0".
warning "@backstage-community/plugin-sonarqube > @backstage-community/plugin-sonarqube-react@0.1.17" has unmet peer dependency "react@^16.13.1 || ^17.0.0 || ^18.0.0".
warning "@backstage-community/plugin-sonarqube > @backstage-community/plugin-sonarqube-react@0.1.17" has unmet peer dependency "react-dom@^16.13.1 || ^17.0.0 || ^18.0.0".
warning "@backstage-community/plugin-sonarqube > @backstage-community/plugin-sonarqube-react@0.1.17" has unmet peer dependency "react-router-dom@6.0.0-beta.0 || ^6.3.0".
warning " > @backstage-community/plugin-sonarqube@0.7.19" has unmet peer dependency "react@^16.13.1 || ^17.0.0 || ^18.0.0".
warning " > @backstage-community/plugin-sonarqube@0.7.19" has unmet peer dependency "react-dom@^16.13.1 || ^17.0.0 || ^18.0.0".
warning " > @backstage-community/plugin-sonarqube@0.7.19" has unmet peer dependency "react-router-dom@6.0.0-beta.0 || ^6.3.0".
[4/4] 🔨  Building fresh packages...
success Saved lockfile.
success Saved 3 new dependencies.
info Direct dependencies
info All dependencies
├─ @backstage-community/plugin-sonarqube-react@0.1.17
├─ @backstage-community/plugin-sonarqube@0.7.19
└─ rc-progress@4.0.0
✨  Done in 17.28s.
skhobrag@Sunils-MacBook-Pro backstage1 % 

```
Add the line below line to the file backstage1/packages/app/src/components/catalog/EntityPage.tsx
  import { EntitySonarQubeCard } from '@backstage-community/plugin-sonarqube';
 <Grid item md={6}>
    <EntitySonarQubeCard variant="gridItem" />
 </Grid>
```bash
skhobrag@Sunils-MacBook-Pro backstage1 %  yarn --cwd packages/backend add @backstage-community/plugin-sonarqube-backend 
yarn add v1.22.22
[1/4] 🔍  Resolving packages...
[2/4] 🚚  Fetching packages...
warning Pattern ["app@link:packages/app"] is trying to unpack in the same destination "/Users/skhobrag/Library/Caches/Yarn/v6/npm-app-0.0.0/node_modules/app" as pattern ["app@0.0.0"]. This could result in non-deterministic behavior, skipping.
[3/4] 🔗  Linking dependencies...
warning "workspace-aggregator-62140bf3-78b3-4cf0-8566-117489f34a79 > app > @backstage/theme@0.5.6" has unmet peer dependency "@types/react@^16.13.1 || ^17.0.0 || ^18.0.0".
warning "workspace-aggregator-62140bf3-78b3-4cf0-8566-117489f34a79 > app > @material-ui/core@4.12.4" has incorrect peer dependency "react@^16.8.0 || ^17.0.0".
warning "workspace-aggregator-62140bf3-78b3-4cf0-8566-117489f34a79 > app > @material-ui/core@4.12.4" has incorrect peer dependency "react-dom@^16.8.0 || ^17.0.0".
warning "workspace-aggregator-62140bf3-78b3-4cf0-8566-117489f34a79 > app > @material-ui/icons@4.11.3" has incorrect peer dependency "react@^16.8.0 || ^17.0.0".
warning "workspace-aggregator-62140bf3-78b3-4cf0-8566-117489f34a79 > app > @material-ui/icons@4.11.3" has incorrect peer dependency "react-dom@^16.8.0 || ^17.0.0".
warning "workspace-aggregator-62140bf3-78b3-4cf0-8566-117489f34a79 > app > @backstage/test-utils@1.5.8" has incorrect peer dependency "@testing-library/react@^15.0.0".
warning "workspace-aggregator-62140bf3-78b3-4cf0-8566-117489f34a79 > app > @backstage-community/plugin-sonarqube > @material-ui/styles@4.11.5" has incorrect peer dependency "react@^16.8.0 || ^17.0.0".
warning "workspace-aggregator-62140bf3-78b3-4cf0-8566-117489f34a79 > app > @backstage-community/plugin-sonarqube > @material-ui/styles@4.11.5" has incorrect peer dependency "react-dom@^16.8.0 || ^17.0.0".
warning "workspace-aggregator-62140bf3-78b3-4cf0-8566-117489f34a79 > app > @backstage/core-components > @material-ui/lab@4.0.0-alpha.61" has incorrect peer dependency "react@^16.8.0 || ^17.0.0".
warning "workspace-aggregator-62140bf3-78b3-4cf0-8566-117489f34a79 > app > @backstage/core-components > @material-ui/lab@4.0.0-alpha.61" has incorrect peer dependency "react-dom@^16.8.0 || ^17.0.0".
warning "workspace-aggregator-62140bf3-78b3-4cf0-8566-117489f34a79 > app > @backstage/plugin-catalog-react > material-ui-popup-state@1.9.3" has incorrect peer dependency "react@^15.0.0 || ^16.0.0 || ^17.0.0".
warning "workspace-aggregator-62140bf3-78b3-4cf0-8566-117489f34a79 > app > @backstage/plugin-scaffolder > @uiw/react-codemirror@4.23.0" has unmet peer dependency "@babel/runtime@>=7.11.0".
warning "workspace-aggregator-62140bf3-78b3-4cf0-8566-117489f34a79 > app > @backstage/plugin-scaffolder > @uiw/react-codemirror@4.23.0" has unmet peer dependency "@codemirror/state@>=6.0.0".
warning "workspace-aggregator-62140bf3-78b3-4cf0-8566-117489f34a79 > app > @backstage/plugin-scaffolder > @uiw/react-codemirror@4.23.0" has unmet peer dependency "@codemirror/theme-one-dark@>=6.0.0".
warning "workspace-aggregator-62140bf3-78b3-4cf0-8566-117489f34a79 > app > @backstage/plugin-scaffolder > @uiw/react-codemirror@4.23.0" has unmet peer dependency "codemirror@>=6.0.0".
warning "workspace-aggregator-62140bf3-78b3-4cf0-8566-117489f34a79 > app > @backstage/plugin-user-settings > @backstage/plugin-signals-react@0.0.4" has incorrect peer dependency "react@^16.13.1 || ^17.0.0".
warning "workspace-aggregator-62140bf3-78b3-4cf0-8566-117489f34a79 > app > @material-ui/core > @material-ui/system@4.12.2" has incorrect peer dependency "react@^16.8.0 || ^17.0.0".
warning "workspace-aggregator-62140bf3-78b3-4cf0-8566-117489f34a79 > app > @material-ui/core > @material-ui/system@4.12.2" has incorrect peer dependency "react-dom@^16.8.0 || ^17.0.0".
warning "workspace-aggregator-62140bf3-78b3-4cf0-8566-117489f34a79 > app > @material-ui/core > @material-ui/utils@4.11.3" has incorrect peer dependency "react@^16.8.0 || ^17.0.0".
warning "workspace-aggregator-62140bf3-78b3-4cf0-8566-117489f34a79 > app > @material-ui/core > @material-ui/utils@4.11.3" has incorrect peer dependency "react-dom@^16.8.0 || ^17.0.0".
warning "workspace-aggregator-62140bf3-78b3-4cf0-8566-117489f34a79 > app > @backstage/core-components > @material-table/core > @material-ui/pickers@3.3.11" has incorrect peer dependency "react@^16.8.0 || ^17.0.0".
warning "workspace-aggregator-62140bf3-78b3-4cf0-8566-117489f34a79 > app > @backstage/core-components > @material-table/core > @material-ui/pickers@3.3.11" has incorrect peer dependency "react-dom@^16.8.0 || ^17.0.0".
warning "workspace-aggregator-62140bf3-78b3-4cf0-8566-117489f34a79 > app > @backstage/plugin-api-docs > @graphiql/react > codemirror-graphql@2.0.12" has unmet peer dependency "@codemirror/language@6.0.0".
warning "workspace-aggregator-62140bf3-78b3-4cf0-8566-117489f34a79 > app > @backstage/plugin-scaffolder > @backstage/plugin-scaffolder-react > use-immer@0.9.0" has unmet peer dependency "immer@>=2.0.0".
warning "workspace-aggregator-62140bf3-78b3-4cf0-8566-117489f34a79 > app > @backstage/plugin-scaffolder > @uiw/react-codemirror > @uiw/codemirror-extensions-basic-setup@4.23.0" has unmet peer dependency "@codemirror/autocomplete@>=6.0.0".
warning "workspace-aggregator-62140bf3-78b3-4cf0-8566-117489f34a79 > app > @backstage/plugin-scaffolder > @uiw/react-codemirror > @uiw/codemirror-extensions-basic-setup@4.23.0" has unmet peer dependency "@codemirror/lint@>=6.0.0".
warning "workspace-aggregator-62140bf3-78b3-4cf0-8566-117489f34a79 > app > @backstage/plugin-scaffolder > @uiw/react-codemirror > @uiw/codemirror-extensions-basic-setup@4.23.0" has unmet peer dependency "@codemirror/search@>=6.0.0".
warning "workspace-aggregator-62140bf3-78b3-4cf0-8566-117489f34a79 > backend > @backstage/plugin-search-backend-module-techdocs > @backstage/plugin-techdocs-node > @aws-sdk/lib-storage@3.616.0" has incorrect peer dependency "@aws-sdk/client-s3@^3.616.0".
warning "workspace-aggregator-62140bf3-78b3-4cf0-8566-117489f34a79 > app > @backstage/plugin-api-docs > swagger-ui-react > swagger-client > ramda-adjunct@5.0.1" has unmet peer dependency "ramda@>= 0.30.0".
warning "workspace-aggregator-62140bf3-78b3-4cf0-8566-117489f34a79 > app > @backstage/plugin-scaffolder > @uiw/react-codemirror > @uiw/codemirror-extensions-basic-setup > @codemirror/autocomplete@6.17.0" has unmet peer dependency "@lezer/common@^1.0.0".
warning "workspace-aggregator-62140bf3-78b3-4cf0-8566-117489f34a79 > backend > @backstage/backend-common > @aws-sdk/credential-providers > @aws-sdk/credential-provider-sso > @aws-sdk/token-providers@3.614.0" has unmet peer dependency "@aws-sdk/client-sso-oidc@^3.614.0".
[4/4] 🔨  Building fresh packages...
success Saved lockfile.
success Saved 2 new dependencies.
info Direct dependencies
info All dependencies
├─ @backstage-community/plugin-sonarqube-backend@0.2.21
└─ app@0.0.0
✨  Done in 14.93s.
skhobrag@Sunils-MacBook-Pro backstage1 % 
```
Add the line below line to the file backstage1/packages/backend/src/index.ts
backend.add(import('@backstage-community/plugin-sonarqube-backend'));

## Enable CircleCI Integration
```bash
skhobrag@Sunils-MacBook-Pro backstage1 %  yarn add --cwd packages/app @circleci/backstage-plugin
yarn add v1.22.22
[1/4] 🔍  Resolving packages...
Couldn't find any versions for "@backstage/catalog-model" that matches "workspace:^"
? Please choose a version of "@backstage/catalog-model" from this list: (Use arrow keys)
❯ 1.5.0 
  1.5.0-next.0 
  1.4.5 
  1.4.5-next.0 
  1.4.4 
  1.4.4-next.0 
  1.4.3 
  1.4.3-next.0 
  1.4.2 
  1.4.2-next.2 
  1.4.2-next.1 
  1.4.2-next.0 
  1.4.1 
  1.4.1-next.0 
  1.4.0 
  1.4.0-next.1 
  1.4.0-next.0 
  1.3.0 
Couldn't find any versions for "@backstage/theme" that matches "workspace:^"
? Please choose a version of "@backstage/theme" from this list: (Use arrow keys)
❯ 0.5.6 
  0.5.6-next.0 
  0.5.5 
  0.5.4 
  0.5.4-next.0 
  0.5.3 
  0.5.2 
  0.5.2-next.0 
  0.5.1 
  0.5.1-next.1 
  0.5.1-next.0 
  0.5.0 
  0.5.0-next.1 
  0.5.0-next.0 
  0.4.4 
  0.4.4-next.0 
  0.4.3 
  0.4.3-next.0 
Couldn't find any versions for "@backstage/core-plugin-api" that matches "workspace:^"
? Please choose a version of "@backstage/core-plugin-api" from this list: (Use arrow keys)
❯ 1.9.3 
  1.9.3-next.0 
  1.9.2 
  1.9.1 
  1.9.1-next.1 
  1.9.1-next.0 
  1.9.0 
  1.9.0-next.1 
  1.8.3-next.0 
  1.8.2 
  1.8.2-next.0 
  1.8.1 
  1.8.1-next.1 
  1.8.1-next.0 
  1.8.0 
  1.8.0-next.0 
  1.7.0 
  1.7.0-next.1 
(Move up and down to reveal more choices)(node:43231) MaxListenersExceededWarning: Possible EventEmitter memory leak detected. 11 keypress listeners added to [ReadStream]. Use emitter.setMaxListeners() to increase limit
(Use `node --trace-warnings ...` to show where the warning was created)
Couldn't find any versions for "@backstage/core-components" that matches "workspace:^"
? Please choose a version of "@backstage/core-components" from this list: (Use arrow keys)
❯ 0.14.9 
  0.14.9-next.1 
  0.14.9-next.0 
  0.14.8 
  0.14.8-next.2 
  0.14.8-next.1 
  0.14.8-next.0 
  0.14.7 
  0.14.7-next.2 
  0.14.6 
  0.14.6-next.1 
  0.14.5 
  0.14.5-next.0 
  0.14.4 
  0.14.4-next.0 
  0.14.3 
  0.14.2 
  0.14.1 
Couldn't find any versions for "@backstage/plugin-catalog-react" that matches "workspace:^"
? Please choose a version of "@backstage/plugin-catalog-react" from this list: 1.12.2
[2/4] 🚚  Fetching packages...
warning Pattern ["app@link:packages/app"] is trying to unpack in the same destination "/Users/skhobrag/Library/Caches/Yarn/v6/npm-app-0.0.0/node_modules/app" as pattern ["app@0.0.0","app@0.0.0"]. This could result in non-deterministic behavior, skipping.
warning Pattern ["@backstage/catalog-model@workspace:^"] is trying to unpack in the same destination "/Users/skhobrag/Library/Caches/Yarn/v6/npm-@backstage-catalog-model-1.5.0-7f5c4a80a3341555db5209fbc6fc2d25f6500707-integrity/node_modules/@backstage/catalog-model" as pattern ["@backstage/catalog-model@^1.5.0","@backstage/catalog-model@^1.5.0","@backstage/catalog-model@^1.5.0","@backstage/catalog-model@^1.5.0","@backstage/catalog-model@^1.5.0","@backstage/catalog-model@^1.5.0","@backstage/catalog-model@^1.5.0","@backstage/catalog-model@^1.5.0","@backstage/catalog-model@^1.5.0","@backstage/catalog-model@^1.5.0","@backstage/catalog-model@^1.5.0","@backstage/catalog-model@^1.5.0","@backstage/catalog-model@^1.5.0","@backstage/catalog-model@^1.5.0","@backstage/catalog-model@^1.5.0","@backstage/catalog-model@^1.5.0","@backstage/catalog-model@^1.5.0","@backstage/catalog-model@^1.5.0","@backstage/catalog-model@^1.5.0","@backstage/catalog-model@^1.5.0","@backstage/catalog-model@^1.5.0","@backstage/catalog-model@^1.5.0","@backstage/catalog-model@^1.5.0","@backstage/catalog-model@^1.5.0","@backstage/catalog-model@^1.5.0","@backstage/catalog-model@^1.5.0","@backstage/catalog-model@^1.5.0","@backstage/catalog-model@^1.5.0","@backstage/catalog-model@^1.5.0","@backstage/catalog-model@^1.5.0","@backstage/catalog-model@^1.5.0","@backstage/catalog-model@^1.5.0"]. This could result in non-deterministic behavior, skipping.
warning Pattern ["@backstage/theme@workspace:^"] is trying to unpack in the same destination "/Users/skhobrag/Library/Caches/Yarn/v6/npm-@backstage-theme-0.5.6-18645cbe42fb5667946e0a5dd38f2fb0bb056597-integrity/node_modules/@backstage/theme" as pattern ["@backstage/theme@^0.5.6","@backstage/theme@^0.5.6","@backstage/theme@^0.5.6","@backstage/theme@^0.5.6","@backstage/theme@^0.5.6","@backstage/theme@^0.5.6","@backstage/theme@^0.5.6","@backstage/theme@^0.5.6","@backstage/theme@^0.5.6","@backstage/theme@^0.5.6"]. This could result in non-deterministic behavior, skipping.
warning Pattern ["@backstage/core-plugin-api@workspace:^"] is trying to unpack in the same destination "/Users/skhobrag/Library/Caches/Yarn/v6/npm-@backstage-core-plugin-api-1.9.3-66b4b7dc620823c66b123c8a2d6db088e2936027-integrity/node_modules/@backstage/core-plugin-api" as pattern ["@backstage/core-plugin-api@^1.9.3","@backstage/core-plugin-api@^1.9.3","@backstage/core-plugin-api@^1.9.3","@backstage/core-plugin-api@^1.9.3","@backstage/core-plugin-api@^1.9.3","@backstage/core-plugin-api@^1.9.3","@backstage/core-plugin-api@^1.9.3","@backstage/core-plugin-api@^1.9.3","@backstage/core-plugin-api@^1.9.3","@backstage/core-plugin-api@^1.9.3","@backstage/core-plugin-api@^1.9.3","@backstage/core-plugin-api@^1.9.3","@backstage/core-plugin-api@^1.9.3","@backstage/core-plugin-api@^1.9.3","@backstage/core-plugin-api@^1.9.3","@backstage/core-plugin-api@^1.9.3","@backstage/core-plugin-api@^1.9.3","@backstage/core-plugin-api@^1.9.3","@backstage/core-plugin-api@^1.9.3","@backstage/core-plugin-api@^1.9.3","@backstage/core-plugin-api@^1.9.3","@backstage/core-plugin-api@^1.9.3","@backstage/core-plugin-api@^1.9.3","@backstage/core-plugin-api@^1.9.3","@backstage/core-plugin-api@^1.9.3","@backstage/core-plugin-api@^1.9.3","@backstage/core-plugin-api@^1.9.3","@backstage/core-plugin-api@^1.9.3","@backstage/core-plugin-api@^1.9.3","@backstage/core-plugin-api@^1.9.3"]. This could result in non-deterministic behavior, skipping.
warning Pattern ["@backstage/core-components@workspace:^"] is trying to unpack in the same destination "/Users/skhobrag/Library/Caches/Yarn/v6/npm-@backstage-core-components-0.14.9-bb1f40be18d8241b70538383d324aec233586382-integrity/node_modules/@backstage/core-components" as pattern ["@backstage/core-components@^0.14.9","@backstage/core-components@^0.14.9","@backstage/core-components@^0.14.9","@backstage/core-components@^0.14.9","@backstage/core-components@^0.14.9","@backstage/core-components@^0.14.9","@backstage/core-components@^0.14.9","@backstage/core-components@^0.14.9","@backstage/core-components@^0.14.9","@backstage/core-components@^0.14.9","@backstage/core-components@^0.14.9","@backstage/core-components@^0.14.9","@backstage/core-components@^0.14.9","@backstage/core-components@^0.14.9","@backstage/core-components@^0.14.9","@backstage/core-components@^0.14.9","@backstage/core-components@^0.14.9","@backstage/core-components@^0.14.9","@backstage/core-components@^0.14.9","@backstage/core-components@^0.14.9","@backstage/core-components@^0.14.9"]. This could result in non-deterministic behavior, skipping.
warning Pattern ["@backstage/plugin-catalog-react@workspace:^"] is trying to unpack in the same destination "/Users/skhobrag/Library/Caches/Yarn/v6/npm-@backstage-plugin-catalog-react-1.12.2-0ec2c3fbe6a5970e498167e06fa55ddf83a2d939-integrity/node_modules/@backstage/plugin-catalog-react" as pattern ["@backstage/plugin-catalog-react@^1.12.2","@backstage/plugin-catalog-react@^1.12.2","@backstage/plugin-catalog-react@^1.12.2","@backstage/plugin-catalog-react@^1.12.2","@backstage/plugin-catalog-react@^1.12.2","@backstage/plugin-catalog-react@^1.12.2","@backstage/plugin-catalog-react@^1.12.2","@backstage/plugin-catalog-react@^1.12.2","@backstage/plugin-catalog-react@^1.12.2","@backstage/plugin-catalog-react@^1.12.2","@backstage/plugin-catalog-react@^1.12.2","@backstage/plugin-catalog-react@^1.12.2","@backstage/plugin-catalog-react@^1.12.2"]. This could result in non-deterministic behavior, skipping.
[3/4] 🔗  Linking dependencies...
warning "workspace-aggregator-c9c07dbd-111c-41c3-9147-4579424f8adb > app > @backstage/theme@0.5.6" has unmet peer dependency "@types/react@^16.13.1 || ^17.0.0 || ^18.0.0".
warning "@circleci/backstage-plugin > @material-ui/core@4.12.4" has unmet peer dependency "react@^16.8.0 || ^17.0.0".
warning "@circleci/backstage-plugin > @material-ui/core@4.12.4" has unmet peer dependency "react-dom@^16.8.0 || ^17.0.0".
warning "@circleci/backstage-plugin > @material-ui/icons@4.11.3" has unmet peer dependency "react@^16.8.0 || ^17.0.0".
warning "@circleci/backstage-plugin > @material-ui/icons@4.11.3" has unmet peer dependency "react-dom@^16.8.0 || ^17.0.0".
warning "@circleci/backstage-plugin > react-use@17.5.1" has unmet peer dependency "react@*".
warning "@circleci/backstage-plugin > react-use@17.5.1" has unmet peer dependency "react-dom@*".
warning "workspace-aggregator-c9c07dbd-111c-41c3-9147-4579424f8adb > app > @backstage/test-utils@1.5.8" has incorrect peer dependency "@testing-library/react@^15.0.0".
warning "workspace-aggregator-c9c07dbd-111c-41c3-9147-4579424f8adb > app > @backstage-community/plugin-sonarqube > @material-ui/styles@4.11.5" has incorrect peer dependency "react@^16.8.0 || ^17.0.0".
warning "workspace-aggregator-c9c07dbd-111c-41c3-9147-4579424f8adb > app > @backstage-community/plugin-sonarqube > @material-ui/styles@4.11.5" has incorrect peer dependency "react-dom@^16.8.0 || ^17.0.0".
warning "@circleci/backstage-plugin > @backstage/core-plugin-api > @backstage/version-bridge@1.0.8" has unmet peer dependency "react@^16.13.1 || ^17.0.0 || ^18.0.0".
warning "@circleci/backstage-plugin > @backstage/core-plugin-api > @backstage/version-bridge@1.0.8" has unmet peer dependency "react-dom@^16.13.1 || ^17.0.0 || ^18.0.0".
warning "@circleci/backstage-plugin > @backstage/core-plugin-api > @backstage/version-bridge@1.0.8" has unmet peer dependency "react-router-dom@6.0.0-beta.0 || ^6.3.0".
warning "@circleci/backstage-plugin > @backstage/core-components > @material-table/core@3.2.5" has unmet peer dependency "react@>=16.8.0".
warning "@circleci/backstage-plugin > @backstage/core-components > @material-table/core@3.2.5" has unmet peer dependency "react-dom@>=16.8.0".
warning "@circleci/backstage-plugin > @material-ui/lab@4.0.0-alpha.61" has unmet peer dependency "react@^16.8.0 || ^17.0.0".
warning "@circleci/backstage-plugin > @material-ui/lab@4.0.0-alpha.61" has unmet peer dependency "react-dom@^16.8.0 || ^17.0.0".
warning "@circleci/backstage-plugin > @backstage/core-components > @react-hookz/web@24.0.4" has unmet peer dependency "react@^16.8 || ^17 || ^18".
warning "@circleci/backstage-plugin > @backstage/core-components > @react-hookz/web@24.0.4" has unmet peer dependency "react-dom@^16.8 || ^17 || ^18".
warning "@circleci/backstage-plugin > @backstage/core-components > linkify-react@4.1.3" has unmet peer dependency "react@>= 15.0.0".
warning "@circleci/backstage-plugin > @backstage/core-components > rc-progress@3.5.1" has unmet peer dependency "react@>=16.9.0".
warning "@circleci/backstage-plugin > @backstage/core-components > rc-progress@3.5.1" has unmet peer dependency "react-dom@>=16.9.0".
warning "@circleci/backstage-plugin > @backstage/core-components > react-helmet@6.1.0" has unmet peer dependency "react@>=16.3.0".
warning "@circleci/backstage-plugin > @backstage/core-components > react-hook-form@7.52.1" has unmet peer dependency "react@^16.8.0 || ^17 || ^18 || ^19".
warning "@circleci/backstage-plugin > @backstage/core-components > react-idle-timer@5.7.2" has unmet peer dependency "react@>=16".
warning "@circleci/backstage-plugin > @backstage/core-components > react-idle-timer@5.7.2" has unmet peer dependency "react-dom@>=16".
warning "@circleci/backstage-plugin > @backstage/core-components > react-markdown@8.0.7" has unmet peer dependency "react@>=16".
warning "@circleci/backstage-plugin > @backstage/core-components > react-sparklines@1.7.0" has unmet peer dependency "react@*".
warning "@circleci/backstage-plugin > @backstage/core-components > react-sparklines@1.7.0" has unmet peer dependency "react-dom@*".
warning "@circleci/backstage-plugin > @backstage/core-components > react-syntax-highlighter@15.5.0" has unmet peer dependency "react@>= 0.14.0".
warning "@circleci/backstage-plugin > @backstage/core-components > react-virtualized-auto-sizer@1.0.24" has unmet peer dependency "react@^15.3.0 || ^16.0.0-alpha || ^17.0.0 || ^18.0.0".
warning "@circleci/backstage-plugin > @backstage/core-components > react-virtualized-auto-sizer@1.0.24" has unmet peer dependency "react-dom@^15.3.0 || ^16.0.0-alpha || ^17.0.0 || ^18.0.0".
warning "@circleci/backstage-plugin > @backstage/core-components > react-window@1.8.10" has unmet peer dependency "react@^15.0.0 || ^16.0.0 || ^17.0.0 || ^18.0.0".
warning "@circleci/backstage-plugin > @backstage/core-components > react-window@1.8.10" has unmet peer dependency "react-dom@^15.0.0 || ^16.0.0 || ^17.0.0 || ^18.0.0".
warning "@circleci/backstage-plugin > @backstage/plugin-catalog-react > @backstage/frontend-plugin-api@0.6.7" has unmet peer dependency "react@^16.13.1 || ^17.0.0 || ^18.0.0".
warning "@circleci/backstage-plugin > @backstage/plugin-catalog-react > @backstage/frontend-plugin-api@0.6.7" has unmet peer dependency "react-router-dom@6.0.0-beta.0 || ^6.3.0".
warning "@circleci/backstage-plugin > @backstage/plugin-catalog-react > material-ui-popup-state@1.9.3" has unmet peer dependency "react@^15.0.0 || ^16.0.0 || ^17.0.0".
warning "workspace-aggregator-c9c07dbd-111c-41c3-9147-4579424f8adb > app > @backstage/plugin-scaffolder > @uiw/react-codemirror@4.23.0" has unmet peer dependency "@babel/runtime@>=7.11.0".
warning "workspace-aggregator-c9c07dbd-111c-41c3-9147-4579424f8adb > app > @backstage/plugin-scaffolder > @uiw/react-codemirror@4.23.0" has unmet peer dependency "@codemirror/state@>=6.0.0".
warning "workspace-aggregator-c9c07dbd-111c-41c3-9147-4579424f8adb > app > @backstage/plugin-scaffolder > @uiw/react-codemirror@4.23.0" has unmet peer dependency "@codemirror/theme-one-dark@>=6.0.0".
warning "workspace-aggregator-c9c07dbd-111c-41c3-9147-4579424f8adb > app > @backstage/plugin-scaffolder > @uiw/react-codemirror@4.23.0" has unmet peer dependency "codemirror@>=6.0.0".
warning "workspace-aggregator-c9c07dbd-111c-41c3-9147-4579424f8adb > app > @backstage/plugin-user-settings > @backstage/plugin-signals-react@0.0.4" has incorrect peer dependency "react@^16.13.1 || ^17.0.0".
warning "@circleci/backstage-plugin > @backstage/theme > @emotion/react@11.13.0" has unmet peer dependency "react@>=16.8.0".
warning "@circleci/backstage-plugin > @backstage/theme > @emotion/styled@11.13.0" has unmet peer dependency "react@>=16.8.0".
warning "@circleci/backstage-plugin > @backstage/theme > @mui/material@5.16.4" has unmet peer dependency "react@^17.0.0 || ^18.0.0".
warning "@circleci/backstage-plugin > @backstage/theme > @mui/material@5.16.4" has unmet peer dependency "react-dom@^17.0.0 || ^18.0.0".
warning "workspace-aggregator-c9c07dbd-111c-41c3-9147-4579424f8adb > app > @material-ui/core > @material-ui/system@4.12.2" has incorrect peer dependency "react@^16.8.0 || ^17.0.0".
warning "workspace-aggregator-c9c07dbd-111c-41c3-9147-4579424f8adb > app > @material-ui/core > @material-ui/system@4.12.2" has incorrect peer dependency "react-dom@^16.8.0 || ^17.0.0".
warning "workspace-aggregator-c9c07dbd-111c-41c3-9147-4579424f8adb > app > @material-ui/core > @material-ui/utils@4.11.3" has incorrect peer dependency "react@^16.8.0 || ^17.0.0".
warning "workspace-aggregator-c9c07dbd-111c-41c3-9147-4579424f8adb > app > @material-ui/core > @material-ui/utils@4.11.3" has incorrect peer dependency "react-dom@^16.8.0 || ^17.0.0".
warning "workspace-aggregator-c9c07dbd-111c-41c3-9147-4579424f8adb > app > @backstage/core-components > @material-table/core > @material-ui/pickers@3.3.11" has incorrect peer dependency "react@^16.8.0 || ^17.0.0".
warning "workspace-aggregator-c9c07dbd-111c-41c3-9147-4579424f8adb > app > @backstage/core-components > @material-table/core > @material-ui/pickers@3.3.11" has incorrect peer dependency "react-dom@^16.8.0 || ^17.0.0".
warning "workspace-aggregator-c9c07dbd-111c-41c3-9147-4579424f8adb > app > @backstage/plugin-api-docs > @graphiql/react > codemirror-graphql@2.0.12" has unmet peer dependency "@codemirror/language@6.0.0".
warning "workspace-aggregator-c9c07dbd-111c-41c3-9147-4579424f8adb > app > @backstage/plugin-scaffolder > @backstage/plugin-scaffolder-react > use-immer@0.9.0" has unmet peer dependency "immer@>=2.0.0".
warning "workspace-aggregator-c9c07dbd-111c-41c3-9147-4579424f8adb > app > @backstage/plugin-scaffolder > @uiw/react-codemirror > @uiw/codemirror-extensions-basic-setup@4.23.0" has unmet peer dependency "@codemirror/autocomplete@>=6.0.0".
warning "workspace-aggregator-c9c07dbd-111c-41c3-9147-4579424f8adb > app > @backstage/plugin-scaffolder > @uiw/react-codemirror > @uiw/codemirror-extensions-basic-setup@4.23.0" has unmet peer dependency "@codemirror/lint@>=6.0.0".
warning "workspace-aggregator-c9c07dbd-111c-41c3-9147-4579424f8adb > app > @backstage/plugin-scaffolder > @uiw/react-codemirror > @uiw/codemirror-extensions-basic-setup@4.23.0" has unmet peer dependency "@codemirror/search@>=6.0.0".
warning "workspace-aggregator-c9c07dbd-111c-41c3-9147-4579424f8adb > backend > @backstage/plugin-search-backend-module-techdocs > @backstage/plugin-techdocs-node > @aws-sdk/lib-storage@3.616.0" has incorrect peer dependency "@aws-sdk/client-s3@^3.616.0".
warning "workspace-aggregator-c9c07dbd-111c-41c3-9147-4579424f8adb > app > @backstage/plugin-api-docs > swagger-ui-react > swagger-client > ramda-adjunct@5.0.1" has unmet peer dependency "ramda@>= 0.30.0".
warning "workspace-aggregator-c9c07dbd-111c-41c3-9147-4579424f8adb > app > @backstage/plugin-scaffolder > @uiw/react-codemirror > @uiw/codemirror-extensions-basic-setup > @codemirror/autocomplete@6.17.0" has unmet peer dependency "@lezer/common@^1.0.0".
warning "workspace-aggregator-c9c07dbd-111c-41c3-9147-4579424f8adb > backend > @backstage/backend-common > @aws-sdk/credential-providers > @aws-sdk/credential-provider-sso > @aws-sdk/token-providers@3.614.0" has unmet peer dependency "@aws-sdk/client-sso-oidc@^3.614.0".
warning "@circleci/backstage-plugin > @backstage/theme@0.5.6" has unmet peer dependency "react@^16.13.1 || ^17.0.0 || ^18.0.0".
warning "@circleci/backstage-plugin > @backstage/theme@0.5.6" has unmet peer dependency "react-dom@^16.13.1 || ^17.0.0 || ^18.0.0".
warning "@circleci/backstage-plugin > @backstage/core-plugin-api@1.9.3" has unmet peer dependency "react@^16.13.1 || ^17.0.0 || ^18.0.0".
warning "@circleci/backstage-plugin > @backstage/core-plugin-api@1.9.3" has unmet peer dependency "react-dom@^16.13.1 || ^17.0.0 || ^18.0.0".
warning "@circleci/backstage-plugin > @backstage/core-plugin-api@1.9.3" has unmet peer dependency "react-router-dom@6.0.0-beta.0 || ^6.3.0".
warning "@circleci/backstage-plugin > @backstage/core-components@0.14.9" has unmet peer dependency "react@^16.13.1 || ^17.0.0 || ^18.0.0".
warning "@circleci/backstage-plugin > @backstage/core-components@0.14.9" has unmet peer dependency "react-dom@^16.13.1 || ^17.0.0 || ^18.0.0".
warning "@circleci/backstage-plugin > @backstage/core-components@0.14.9" has unmet peer dependency "react-router-dom@6.0.0-beta.0 || ^6.3.0".
warning "@circleci/backstage-plugin > @backstage/plugin-catalog-react@1.12.2" has unmet peer dependency "react@^16.13.1 || ^17.0.0 || ^18.0.0".
warning "@circleci/backstage-plugin > @backstage/plugin-catalog-react@1.12.2" has unmet peer dependency "react-dom@^16.13.1 || ^17.0.0 || ^18.0.0".
warning "@circleci/backstage-plugin > @backstage/plugin-catalog-react@1.12.2" has unmet peer dependency "react-router-dom@6.0.0-beta.0 || ^6.3.0".
warning " > @circleci/backstage-plugin@0.1.1" has unmet peer dependency "react@^16.13.1 || ^17.0.0".
warning " > @circleci/backstage-plugin@0.1.1" has unmet peer dependency "react-dom@^16.13.1 || ^17.0.0".
warning " > @circleci/backstage-plugin@0.1.1" has unmet peer dependency "react-router-dom@6.0.0-beta.0 || ^6.3.0".
[4/4] 🔨  Building fresh packages...
success Saved lockfile.
success Saved 2 new dependencies.
info Direct dependencies
info All dependencies
├─ @circleci/backstage-plugin@0.1.1
└─ circleci-api@4.1.4
✨  Done in 39.38s.
skhobrag@Sunils-MacBook-Pro backstage1 % 

```


