# vue-tsc-import-resolution

A reproduction for volar auto import resolution not working for monorepos

# takeover mode: off

When takeover mode is off it is able to auto import the modules/dependencies from external workspaces/packages

- Enable the built-in TypeScript Extension
  - Run Extensions: Show Built-in Extensions from VSCode's command palette
  - Find TypeScript and JavaScript Language Features, right click and select Enable (Workspace)
- Reload the VSCode window by running Developer: Reload Window from the command palette.
- Within `./packages/main/src/index.ts` try to use `isFalse` function from `b` package. 
  - The exported function is found in intelisense and choosing that will auto import the dependency.

# takeover mode: on

When takeover mode is on it is unable to auto import modules/dependencies from external workspaces/packages

- Enable the built-in TypeScript Extension
  - Run Extensions: Show Built-in Extensions from VSCode's command palette
  - Find TypeScript and JavaScript Language Features, right click and select Disable (Workspace)
- Reload the VSCode window by running Developer: Reload Window from the command palette.
- Within `./packages/main/src/index.ts` try to use `isFalse` function from `b` package. 
  - The exported function is not found in intelisense
