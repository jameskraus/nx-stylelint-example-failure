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