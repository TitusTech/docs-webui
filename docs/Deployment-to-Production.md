---
title: Deployment to Production
permalink: /docs/Deployment-to-Production/
---

### Generate a release

* Go to the webui-lib directory:
```
cd ~/workspace/titus/webui-lib
```
* Merge latest changes into `3atech_master` branch:
```
git checkout 3atech
git pull -r
git checkout 3atech_master
git pull -r
git merge 3atech
```

* Change version number in the 3rd line of all of these files:
```
vim package.json 
vim projects/webui-library/package.json
vim src/environments/environment.prod.ts
```

* Commit changes:
```
git status
git diff
git add .
git commit -m 'Change version number to 0.0.0'
git push origin HEAD -u
```

* Build and publish:
```
npm install
ng build --prod webui-library
cd dist/webui-library
npm pack
npm publish
```

### Optimize for production

Although deploying directly from the development environment works, you can generate an optimized build with additional CLI command line flags, starting with `--prod`:

```
ng build --prod
```

The `--prod` meta-flag engages the following optimization features.

* Ahead-of-Time (AOT) Compilation: pre-compiles Angular component templates.
* Production mode: deploys the production environment which enables production mode.
* Bundling: concatenates your many application and library files into a few bundles.
* Minification: removes excess whitespace, comments, and optional tokens.
* Uglification: rewrites code to use short, cryptic variable and function names.
* Dead code elimination: removes unreferenced modules and much unused code.

This generated build artifacts to the output folder in `dist/` by default.

