# vsf-capybara

# Coding Standards

## Do

* Follow official style guide https://vuejs.org/v2/style-guide/.
* Use ESLint on before commit hook.
* Use Prettier on before commit hook.
* At least 1 person code review for Pull Requests.
* Always start the implementation of new pages with Storefront UI Pages.
* Use Storefront UI CSS. Do not reinvent the wheel.

## Do not

* Do not follow Vue Storefront 1 Theme Style Guide. Stick to official Vue.js Style Guide.
* Avoid importing CSS to components.

# Definition of Ready

## User Stories

* User Story format to create Github issues is used - I want to `<goal>` So that `<reason>`. Yes, we skip the persona.
* Milestone / epic is assigned.
* Acceptance criteria are listed.
* User story is small enough to be completed in one sprint.
* Team knows what to do, and do not see any blocking points.

## Bugs

* Current behavior is explained.
* Expected behavior is explained.
* Steps to reproduce are provided.
* Screenshot or gif is provided, if possible.

# Definition of Done

* Branch is merged to master.
* Unit tests are written (if reasonable).
* Passed code review. All suggestions are resolved.
* Code meets our Coding Standards.

# Testing approach

* Unit tests written, if reasonable.
* End-to-end coverage to be discussed at the end of 2019 December.

# Roadmap 2019-12-02

![Roadmap of vsf-capybara](https://github.com/DivanteLtd/vsf-capybara/blob/master/capybara_roadmap_20191202.jpg "Roadmap of vsf-capybara")

---

# Development environment setup

* Install `lerna` globally: `npm install -g lerna`
* Configure `vsf-capybara` repo as a git submodule in theme path of your `vue-storefront` workspace and track `master` branch: `git submodule add -b master https://github.com/DivanteLtd/vsf-capybara src/themes/capybara`
* Fetch all the data: `git submodule update --init --remote`
* Update VS configuration by copying `local.json` file to root `config` directory
* Update TypeScript compiler option in `compilerOptions.paths.theme/*` from default theme `["src/themes/default/*"]` to brand new `capybara` theme: `["src/themes/capybara/*"]`
* Download all dependencies and start dev server: `lerna bootstrap && yarn dev`