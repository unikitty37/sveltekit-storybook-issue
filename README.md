# sv

Create a project, selecting the following options:

```
$ pnpx sv create testapp
Packages: +1
+
Progress: resolved 1, reused 0, downloaded 1, added 1, done
┌  Welcome to the Svelte CLI! (v0.6.10)
│
◇  Which template would you like?
│  SvelteKit minimal
│
◇  Add type checking with Typescript?
│  Yes, using Typescript syntax
│
◆  Project created
│
◇  What would you like to add to your project? (use arrow keys / space bar)
│  storybook
│
◇  Which package manager do you want to install dependencies with?
│  pnpm
│
◇  Running external command (pnpm dlx storybook@latest init --skip-install --no-dev)
```

Attempt to start the Storybook server:

```
cd testapp
pnpm run storybook --no-open
```

And it fails:

```
@storybook/core v8.4.7

SB_CORE-SERVER_0002 (CriticalPresetLoadError): Storybook failed to load the following preset: ./.storybook/main.js.

Please check whether your setup is correct, the Storybook dependencies (and their peer dependencies) are installed correctly and there are no package version clashes.

If you believe this is a bug, please open an issue on Github.

SB_CORE-SERVER_0002 (CriticalPresetLoadError): Storybook failed to load the following preset: ./node_modules/.pnpm/@storybook+addon-svelte-csf@5.0.0-next.21_@storybook+svelte@8.4.7_storybook@8.4.7_svelte@5.16_tyhb6bhjyuiufyc5upvydfzfzy/node_modules/@storybook/addon-svelte-csf/dist/preset.js.

Please check whether your setup is correct, the Storybook dependencies (and their peer dependencies) are installed correctly and there are no package version clashes.

If you believe this is a bug, please open an issue on Github.

Error [ERR_MODULE_NOT_FOUND]: Cannot find module './node_modules/.pnpm/@storybook+addon-svelte-csf@5.0.0-next.21_@storybook+svelte@8.4.7_storybook@8.4.7_svelte@5.16_tyhb6bhjyuiufyc5upvydfzfzy/node_modules/@storybook/addon-svelte-csf/dist/utils/identifier-utils' imported from ./node_modules/.pnpm/@storybook+addon-svelte-csf@5.0.0-next.21_@storybook+svelte@8.4.7_storybook@8.4.7_svelte@5.16_tyhb6bhjyuiufyc5upvydfzfzy/node_modules/@storybook/addon-svelte-csf/dist/compiler/pre-transform/codemods/legacy-story.js
    at finalizeResolution (node:internal/modules/esm/resolve:275:11)
    at moduleResolve (node:internal/modules/esm/resolve:932:10)
    at defaultResolve (node:internal/modules/esm/resolve:1056:11)
    at ModuleLoader.defaultResolve (node:internal/modules/esm/loader:654:12)
    at #cachedDefaultResolve (node:internal/modules/esm/loader:603:25)
    at ModuleLoader.getModuleJobForRequire (node:internal/modules/esm/loader:353:53)
    at new ModuleJobSync (node:internal/modules/esm/module_job:341:34)
    at ModuleLoader.getModuleJobForRequire (node:internal/modules/esm/loader:413:11)
    at new ModuleJobSync (node:internal/modules/esm/module_job:341:34)
    at ModuleLoader.getModuleJobForRequire (node:internal/modules/esm/loader:413:11)

More info:

    at loadPreset (./node_modules/.pnpm/@storybook+core@8.4.7/node_modules/@storybook/core/dist/common/index.cjs:16477:13)

More info:

    at loadPreset (./node_modules/.pnpm/@storybook+core@8.4.7/node_modules/@storybook/core/dist/common/index.cjs:16477:13)
    at async Promise.all (index 1)
    at async loadPresets (./node_modules/.pnpm/@storybook+core@8.4.7/node_modules/@storybook/core/dist/common/index.cjs:16487:55)
    at async getPresets (./node_modules/.pnpm/@storybook+core@8.4.7/node_modules/@storybook/core/dist/common/index.cjs:16520:11)
    at async buildDevStandalone (./node_modules/.pnpm/@storybook+core@8.4.7/node_modules/@storybook/core/dist/core-server/index.cjs:37145:11)
    at async withTelemetry (./node_modules/.pnpm/@storybook+core@8.4.7/node_modules/@storybook/core/dist/core-server/index.cjs:35757:12)
    at async dev (./node_modules/.pnpm/@storybook+core@8.4.7/node_modules/@storybook/core/dist/cli/bin/index.cjs:2591:3)
    at async s.<anonymous> (./node_modules/.pnpm/@storybook+core@8.4.7/node_modules/@storybook/core/dist/cli/bin/index.cjs:2643:74)

WARN Broken build, fix the error above.
WARN You may need to refresh the browser.

WARN   Failed to load preset: {"type":"presets","name":"/workspaces/testapp/node_modules/.pnpm/@storybook+addon-svelte-csf@5.0.0-next.21_@storybook+svelte@8.4.7_storybook@8.4.7_svelte@5.16_tyhb6bhjyuiufyc5upvydfzfzy/node_modules/@storybook/addon-svelte-csf/dist/preset.js"} on level 1
Error [ERR_MODULE_NOT_FOUND]: Cannot find module './node_modules/.pnpm/@storybook+addon-svelte-csf@5.0.0-next.21_@storybook+svelte@8.4.7_storybook@8.4.7_svelte@5.16_tyhb6bhjyuiufyc5upvydfzfzy/node_modules/@storybook/addon-svelte-csf/dist/utils/identifier-utils' imported from ./node_modules/.pnpm/@storybook+addon-svelte-csf@5.0.0-next.21_@storybook+svelte@8.4.7_storybook@8.4.7_svelte@5.16_tyhb6bhjyuiufyc5upvydfzfzy/node_modules/@storybook/addon-svelte-csf/dist/compiler/pre-transform/codemods/legacy-story.js
    at finalizeResolution (node:internal/modules/esm/resolve:275:11)
    at moduleResolve (node:internal/modules/esm/resolve:932:10)
    at defaultResolve (node:internal/modules/esm/resolve:1056:11)
    at ModuleLoader.defaultResolve (node:internal/modules/esm/loader:654:12)
    at #cachedDefaultResolve (node:internal/modules/esm/loader:603:25)
    at ModuleLoader.getModuleJobForRequire (node:internal/modules/esm/loader:353:53)
    at new ModuleJobSync (node:internal/modules/esm/module_job:341:34)
    at ModuleLoader.getModuleJobForRequire (node:internal/modules/esm/loader:413:11)
    at new ModuleJobSync (node:internal/modules/esm/module_job:341:34)
    at ModuleLoader.getModuleJobForRequire (node:internal/modules/esm/loader:413:11)
 ELIFECYCLE  Command failed with exit code 1.
```
