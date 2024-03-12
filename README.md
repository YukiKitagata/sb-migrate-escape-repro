# sb-migrate-escape-repro

This repository is a reproduction of a bug caused by the improper path escaping in the Storybook migrate command.

# How to reproduce

1. Clone this repository
2. Run `npx storybook@latest migrate csf-2-to-3 --glob="**/*.stories.tsx" --parser=tsx` in the root of the repository

# Expected behavior

The command should run successfully and migrate the stories.

# Actual behavior

The command fails with the following error:

```
=> Applying csf-2-to-3: 1 files
/bin/sh: -c: line 0: syntax error near unexpected token `('
/bin/sh: -c: line 0: `node /Users/yuki/.npm/_npx/bc7e1e37fcb46ffc/node_modules/jscodeshift/bin/jscodeshift.js --no-babel --extensions=tsx --fail-on-error -t /Users/yuki/.npm/_npx/bc7e1e37fcb46ffc/node_modules/@storybook/codemod/dist/transforms/csf-2-to-3.js --parser tsx (folder)/test.stories.tsx'
```
