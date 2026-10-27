## Contributing

We welcome contributions to Tribute. There are many areas where we would love to see community contributions that we have outlined below, but first, let's go over how to develop in Tribute. We use [Yarn 4](https://yarnpkg.com/getting-started/install), pinned in `package.json` through Corepack, to manage our NPM packages. Use Node.js 24 (see `.nvmrc`) for development and CI. This tooling version does not change the published library's runtime requirements.

Install dependencies:

```sh
corepack enable
corepack install
yarn install --immutable
```

Yarn uses the `node-modules` linker and a five-day cooldown for new dependency resolutions. Commit `yarn.lock` changes when deliberately updating dependencies; do not create an npm lockfile. Generated Yarn cache/install state stays untracked.

Run Rollup:

```sh
yarn start
```

That's it! Now you can use the `example/index.html` to test out changes to the code base. All changes to `src` will recompile on the fly.

Once you have made your changes, feel free to submit a pull request.

## Testing

We use [Karma](https://karma-runner.github.io/latest/index.html) and [Jasmin](https://jasmine.github.io) as the testing framework.

To run the tests type:

```
yarn run build
yarn test
```

GitHub Actions builds the library and runs the browser suite on pull requests and pushes
to `reviewable-master` or `release`. CI uses the runner's installed Chrome via `CHROME_BIN`
and skips Puppeteer's Chromium download. You can set `CHROME_BIN` locally to use an installed
Chrome as well; otherwise Karma uses Puppeteer's bundled browser.

## Contribution Ideas

The major focus that we could use your help with is creating wrappers for different JavaScript frameworks. Some of the ones we are interested in are outlined below. We also see a couple of areas for improving compatibility with different rendering situations, such as in iframes inside of rich text editors.

**Some ideas that are for grabs**

- Prosemirror component
- `noMatchTemplate` per collection.
