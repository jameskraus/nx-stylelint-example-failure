# NxStylelintExampleFailure


Example of invalid CSS generated from the default NX setup for emotion with a default react library, causing stylelint to fail.

## Reproducing

To setup, run `npm install`

Run `npx stylelint "**/*.tsx"` to see the failure:

```
apps/my-app/src/app/app.tsx
  5:3  ✖  Unknown word //  CssSyntaxError

✖ 1 problem (1 error, 0 warnings)
```

This is because apps/my-app/src/app/app.tsx is using `//` comments instead of `/*` comments. `//` comments are not actually in the CSS spec, but are usually ignored by browsers.

## How was this app generated, anyways?

With these settings:

```
> npx nx g @nx/react:application apps/my-app

 NX  Generating @nx/react:application

✔ Which stylesheet format would you like to use? · @emotion/styled
✔ Would you like to add routing to this application? (y/N) · false
✔ Which bundler do you want to use to build the application? · vite
✔ Which linter would you like to use? · none
✔ What unit test runner should be used? · none
✔ Which E2E test runner would you like to use? · playwright
✔ Which port would you like to use for the dev server? · 4200
```