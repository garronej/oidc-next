<p align="center">
    <img src="https://user-images.githubusercontent.com/6702424/80216211-00ef5280-863e-11ea-81de-59f3a3d4b8e4.png">  
</p>
<p align="center">
    <i>Potential nex name for oidc-spa when we have Nuxt and Next.js adapter (claming the NPM name)</i>
    <br>
    <br>
    <a href="https://github.com/garronej/oidc-next/actions">
      <img src="https://github.com/garronej/oidc-next/actions/workflows/ci.yaml/badge.svg?branch=main">
    </a>
    <a href="https://bundlephobia.com/package/oidc-next">
      <img src="https://img.shields.io/bundlephobia/minzip/oidc-next">
    </a>
    <a href="https://www.npmjs.com/package/oidc-next">
      <img src="https://img.shields.io/npm/dw/oidc-next">
    </a>
    <a href="https://github.com/garronej/oidc-next/blob/main/LICENSE">
      <img src="https://img.shields.io/npm/l/oidc-next">
    </a>
</p>
<p align="center">
  <a href="https://github.com/garronej/oidc-next">Home</a>
  -
  <a href="https://github.com/garronej/oidc-next">Documentation</a>
</p>

# Install / Import

```bash
$ npm install --save oidc-next
```

```typescript
import { myFunction, myObject, MyReactComponent } from "oidc-next";
```

Specific imports, only import what you need:

```typescript
import { myFunction } from "oidc-next/myFunction";
import { myObject } from "oidc-next/myObject";
import MyReactComponent from "oidc-next/MyReactComponent";
```

# Contributing

## Testing your changes in an external app

You have made some changes to the code and you want to test them
in your app before submitting a pull request?

Assuming `you/my-app` have `oidc-next` as a dependency.

```bash
cd ~/github
git clone https://github.com/you/my-app
cd my-app
yarn

cd ~/github
git clone https://github.com/garronej/oidc-next
cd oidc-next
yarn
yarn build
yarn link-in-app my-app
npx tsc -w

# Open another terminal

cd ~/github/my-app
rm -rf node_modules/.cache
yarn start # Or whatever my-app is using for starting the project
```

You don't have to use `~/github` as reference path. Just make sure `my-app` and `oidc-next`
are in the same directory.

> Note for the maintainer: You might run into issues if you do not list all your singleton dependencies in
> `src/link-in-app.js -> singletonDependencies`. A singleton dependency is a dependency that can
> only be present once in an App. Singleton dependencies are usually listed as peerDependencies example `react`, `@emotion/*`.

## Releasing

For releasing a new version on GitHub and NPM you don't need to create a tag.  
Just update the `package.json` version number and push.

For publishing a release candidate update your `package.json` with `1.3.4-rc.0` (`.1`, `.2`, ...).  
It also work if you do it from a branch that have an open PR on main.

> Make sure your have defined the `NPM_TOKEN` repository secret or NPM publishing will fail.
