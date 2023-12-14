# finance

Repository for the v2 UI of lux.

## Setup

```bash
git clone https://github.com/lux-finance/lux-v2-frontend
cd lux-v2-frontend
cp .env.demo .env
yarn install
```

Fill the `.env` file with the required secrets.

Start local development server using `yarn dev` to fetch latest contract artifacts, or use `yarn dev:noabi` to skip that.

The app should be accessible on [localhost:5005](http://localhost:5005) by default.

## Contributing

### Branches

This repository is using two main branches for deployments:

- The [production deployment](https://lux.finance/) is built using `main` branch codebase
- The [beta deployment](https://beta.lux.finance/) is built using `beta` branch codebase

New branches, when pushed, will also be built using our Vercel CI/CD pipeline, so minimize unneccessary pushes to tracked branches.

In general the process to contribute to the codebase looks like this:

- Find [issue](https://github.com/luxdefi/finance/issues) or new feature you want to work on
- Branch off of `beta` and use that as your working branch
- Once ready, a pull request is supposed to be opened to merge your branch into `beta`

With the next deployment cycle, `beta` and all changes in it will be merged into `prod`.

Use descriptive language in your commit messages. Nobody likes to chase down changes to understand what is supposed to be changed.

### Codestyle

To make it easier for all contributors, please respect the codestyle rules.

Disable hard wrapping on save in your editor for markdown files.

**Note:** this requires you to have done the steps in `Setup` first.

#### Webstorm

Open Webstorm settings and navigate to `Preferences/Languages & Frameworks/JavaScript/Prettier`, select the Prettier install from the local `node_modules` directory, add `svelte` to the glob pattern and enable `Run on save for files`.

Source: [prettier.io docs](https://prettier.io/docs/en/webstorm.html)

Next, navigate to `Editor & Code Style`, select `Project` in the scheme dropdown, click the `Formatter` tab and add `*.md` to the 'Do not Format' list.

#### VS Code

##### Using Svelte extension (recommended)

Install the `svelte-vscode` extension either through the marketplace, or by using the quick open command and pasting `ext install JamesBirtles.svelte-vscode`. Make sure VS Code settings includes

```json
{
  "[svelte]": {
    "editor.defaultFormatter": "svelte.svelte-vscode"
  }
}
```

Source: [svelte-vscode marketplace](https://marketplace.visualstudio.com/items?itemName=svelte.svelte-vscode)

##### Using Prettier extension

Install the `prettier-vscode` extension either through the marketplace, or by using the quick open command and pasting `ext install esbenp.prettier-vscode`. Make sure VS Code settings includes

```json
{
  "editor.defaultFormatter": "esbenp.prettier-vscode"
}
```

You may also adjust that setting on a per language basis.

Source: [prettier-vscode Github](https://github.com/prettier/prettier-vscode)
