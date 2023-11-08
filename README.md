# Example
This sample project shows the issue described here: https://github.com/TypeStrong/ts-node/issues/1989

Ts-config depends not on the path of the executed file but on the path from where it is called.

Such a behavior prevents us considering esm loader for CLI scenarios.

To see it you can run `npm run fail`. `npm run success` shows the current workaround

## Current behavior

- `npx ts-node-sample` on the root level fails (because no tsconfig on the top-level)
- `npx -w samples/ts-node ts-node-sample` on the root level works because we mention the workspace where to run this command
- `npx tsx tsx-sample` just works

## Expected behavior
`npx ts-node-sample` on the root level should also work since the base folder of executable file is `samples/ts-node` also containing tsconfig.json


