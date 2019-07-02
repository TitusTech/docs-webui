---
title: Deployment-to-Production
permalink: /docs/Deployment-to-Production/
---

## Optimize for production

Although deploying directly from the development environment works, you can generate an optimized build with additional CLI command line flags, starting with --prod.
Build with --prod

      

### ng build --prod

The --prod meta-flag engages the following optimization features.

    * Ahead-of-Time (AOT) Compilation: pre-compiles Angular component templates.
    * Production mode: deploys the production environment which enables production mode.
    * Bundling: concatenates your many application and library files into a few bundles.
    * Minification: removes excess whitespace, comments, and optional tokens.
    * Uglification: rewrites code to use short, cryptic variable and function names.
    * Dead code elimination: removes unreferenced modules and much unused code.

This generated build artifacts to the output folder in dist/ by default.