# rhino (development version)

# [rhino 1.6.0](https://github.com/Appsilon/rhino/releases/tag/v1.6.0)

1. `pkg_install` supports installation from local sources, GitHub, and Bioconductor.
2. Improve Rhino CI (use latest versions and make better use of actions).
3. Upgrade tools based on Node.js:
    * `test_e2e()` now uses `cypress` 13.6
    * `build_js()` now uses `webpack` 5.89
    * `build_sass()` now uses `sass` 1.69
    * `lint_js()` now uses `eslint` 8.56
    * `lint_sass()` now uses `stylelint` 14.16 (the last major version supporting stylistic rules)
    * Upgrade all remaining Node.js dependencies to latest versions and fix vulnerabilities.
    * The minimum supported Node.js version is now 16.
4. Introduce `RHINO_NPM` environment variable
to allow using `npm` alternatives like `bun` and `pnpm`.

# [rhino 1.5.0](https://github.com/Appsilon/rhino/releases/tag/v1.5.0)

1. Add Rstudio Addins for lint, build and test Sass, R and JavaScript. Updated new module Addin.
2. Fixes timeout during Cypress E2E tests with GitHub Actions.
3. `format_r` no longer adds spaces in `box` imports.
4. `build_sass` minifies the CSS file also if using R `sass` package.

# [rhino 1.4.0](https://github.com/Appsilon/rhino/releases/tag/v1.4.0)

1. New `pkg_install()` and `pkg_remove()` functions to simplify dependency management in Rhino.
2. Add support for using React in Rhino
(tutorial, JS function `registerReactComponents()`, R function `react_component()`).
3. Require box v1.1.3 or later (fixes issues with lazy-loaded data and trailing commas).
4. Add E2E tests for the Rhino package (internal).

# [rhino 1.3.1](https://github.com/Appsilon/rhino/releases/tag/v1.3.1)

1. `test_r()` now clears the environment of loaded box modules before tests are run.
This removes the need for `box::reload()` calls in tests.
2. Added support for `shinymanager`.

# [rhino 1.3.0](https://github.com/Appsilon/rhino/releases/tag/v1.3.0)

1. Rhino now works with `shinytest2` out of the box.

# [rhino 1.2.1](https://github.com/Appsilon/rhino/releases/tag/v1.2.1)

1. Fix Rhino GitHub Actions (Cypress used to fail).

# [rhino 1.2.0](https://github.com/Appsilon/rhino/releases/tag/v1.2.0)

1. Don't use symbolic links internally.
This fixes a couple of issues with Node.js tools on Windows:
    * Developer Mode is no longer needed.
    * The `build_js()` and `build_sass()` functions now work with `watch = TRUE`.
    * The `lint_js()` function now works when imports are used in JavaScript.
2. Drop dependency on Yarn - only Node.js is now required.
3. Improved Rhino CI:
    * Run `build_js()` and `build_sass()` CI.
    * Use R version from the lockfile.
    * Upgrade to `r-lib/actions/setup-r@v2`.
4. The `lint_r()` now accepts a `paths` argument which can be used to run it on specific files.
5. The `init()` function will refuse to run in the home directory unless `force = TRUE` is passed.
6. Shiny bookmarking works better with `legacy_entrypoint: source`
(the UI function no longer needs to take an argument).
7. Upgraded to `lintr >= 3.0.0` and updated linter rules.

# [rhino 1.1.1](https://github.com/Appsilon/rhino/releases/tag/v1.1.1)

Minor release to fix CRAN check failures (upgrade roxygen2 to 7.2.1 and regenerate documentation).

# [rhino 1.1.0](https://github.com/Appsilon/rhino/releases/tag/v1.1.0)

1. New guide:  "How to manage secrets and environments" (#263).
2. Sass-specific at-rules are now recognized by `rhino::lint_sass()` (#289).
3. Shiny bookmarking now works (#294).
4. RStudio no longer complains about "too many files" during push-button deployment (#299).
5. Issues with server reloading during development resolved (#297).

# [rhino 1.0.0](https://github.com/Appsilon/rhino/releases/tag/v1.0.0)

First stable version.
