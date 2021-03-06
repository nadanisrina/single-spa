# Frontend Booster - React SPA (Single Page Application)

This codebase is a React SPA boilerplate. It is intended to be used as a
[Booster](https://github.com/jared-jewitt/booster-guidelines) for my [Launchpad](https://github.com/jared-jewitt/launchpad).
However, that being said, it can still be used completely on its own.

#### Requirements:

- [Docker](https://www.docker.com/)
- [WSL](https://docs.microsoft.com/en-us/windows/wsl/install-win10) - Only for Windows users

#### Features:

- โ๏ธ React 17
- โ๏ธ Type safety via TypeScript
- ๐ Private and public routes
- ๐ฆ Babel + Webpack for code transpilation and bundling
- ๐ Write SCSS & future CSS with PostCSS + preset-env
- ๐ฏ Browserslist for specific browser support
- ๐ Add SVGs, images, and custom fonts
- ๐ Path aliasing for streamlined imports
- ๐ Prettier + ESLint + StyleLint for consistent code style
- ๐บ Husky + lint-staged for code quality assurance
- ๐งช Mocha + Cypress for unit and integration tests

#### Developers:

- [Jared Jewitt](https://jared-jewitt.github.io)

---

### ๐ Getting Started

Starting the fully-fledged frontend is as simple as running the commands below.

```shell
sh setup.sh

make client
```

- The client container exposes port 4000 and can be viewed by visiting http://localhost:4000

### โจ๏ธ Commands

###### Make

| Command       | Description                                                                      |
| ------------- | -------------------------------------------------------------------------------- |
| `make client` | Launches the client container                                                    |
| `make down`   | Removes the client containers                                                    |
| `make nuke`   | Purges all client containers, images, networks, volumes                          |
| `make bash`   | Shells into the client to run one-off commands. e.g. `npm run test:e2e:headless` |

###### NPM

| Command                     | Description                                                                 |
| --------------------------- | --------------------------------------------------------------------------- |
| `npm run build`             | Bundles the app into a single `build` folder                                |
| `npm run prod`              | Runs the client on $PORT &#124;&#124; 4002 (must run `npm run build` first) |
| `npm run dev`               | Runs the client with hot reloading on $PORT &#124;&#124; 4000               |
| `npm run test`              | Runs the suite of unit and e2e tests                                        |
| `npm run test:unit`         | Runs the suite of unit tests                                                |
| `npm run test:e2e`          | Runs the suite of end-to-end tests with real browser interactivity          |
| `npm run test:e2e:headless` | Runs the suite of end-to-end tests in headless mode                         |

### ๐ฑ Environment Variables

Environment variables are injected into the app at runtime. To add a new environment variable, you will need to update
the following files:

- [.env.production.local](.env.production.local) - Loads environment variables for the app at runtime in prod mode
- [.env.development.local](.env.development.local) - Loads environment variables for the app at runtime in dev mode
- [.env.test.local](.env.test.local) - Loads environment variables for the app at runtime in test mode

Please note the environment variables in each of these places are only used when running the app locally. If you are
deploying this app, it is expected you specify env vars on the hosted server and reference them in
[google-cloud-build/build.yaml](google-cloud-build/build.yaml) and
[google-cloud-build/promote.yaml](google-cloud-build/promote.yaml). See [deployment](DEPLOYMENT.md).

### ๐ Deployment

[Instructions here](DEPLOYMENT.md)

### โ๏ธ License

Code released under the [MIT License](LICENSE)
