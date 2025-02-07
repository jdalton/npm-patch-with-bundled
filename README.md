# npm-patch-with-bundled

# Steps

 - Run `npm ci` (notice no errors)
 - Run `npm i` (from the patched of https://github.com/npm/cli/pull/7025 or v11)
 - Notice the `package-lock.json` has changed
 - Run `npm ci` again (notice it errors)
 > pm ERR! code EUSAGE
npm ERR!
npm ERR! `npm ci` can only install packages when your package.json and package-lock.json or npm-shrinkwrap.json are in sync. Please update your lock file with `npm install` before continuing.
npm ERR!
npm ERR! Missing: call-bind@1.0.8 from lock file
npm ERR! Missing: get-intrinsic@1.2.7 from lock file
npm ERR!

- Run `npm install --ignore-scripts --package-lock-only` (notice lockfile mostly reverts)
- Run `npm ci` (notice no error)