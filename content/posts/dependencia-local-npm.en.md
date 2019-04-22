---
title: "Use a local dependency with NPM or Yarn"
date: 2019-04-22T15:49:17-04:00
draft: false
---

While in most cases we add packages to our project with `npm install [DEPENDENCY_NAME]` we might want to use a local version, for instance, if we are developing a new library or modifying an existing one.

In these cases **npm** (and **yarn** too) allows us to link this local library as a dependency to our project:

- In the local library directory:
    - If using **npm**: `npm link`
    - When using **yarn**: `yarn link`
- In our project directory:
    - With **npm**: `npm link [DEPENDENCY_NAME]`
    - Using **yarn**: `yarn link [DEPENDENCY_NAME]`

Done!

To unlink:

- If using **npm**, run the following:
    - `npm rm --global [NOMBRE_DEPENDENCIA]`
- When using yarn **yarn**:
    - In our project directory, run:
        - `yarn unlink [NOMBRE_DEPENDENCIA]`
    - Then in the local library directory run:
        - `yarn unlink`