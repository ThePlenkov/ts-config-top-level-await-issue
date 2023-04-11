# Example
This sample project shows the issue described here: https://github.com/TypeStrong/ts-node/issues/1989

Ts-config depends not on the path of the executed file but on the path from where it is called.

Such a behavior prevents us considering esm loader for CLI scenarios.

To see it you can run `npm run fail`. `npm run success` shows the current workaround

## Current behavior

`npx codegen` on the root level fails
`npx codegen` on the `tools/codegen` level works

## Expected behavior
`npx codegen` on the root level should also work since the base folder is `tools/codegen` , not root for the typescript file.


