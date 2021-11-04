# Yarn workspaces spike

## Root package.json

```
"workspaces": [
    "packages/*"
  ],
```

`yarn workspaces list``

## Working in a concrete workspace

```
yarn workspace workspace-name start
yarn workspace workspace-name test
yarn workspace workspace-name run build
yarn workspace workspace-name add react
yarn workspace foreach test
```

## Build only workspaces with changes

https://yarnpkg.com/cli/workspaces/foreach

```
yarn workspaces foreach --since run build
```

## Import a workspace from another

Workspace A wants to import Workspace B.

1. Go to A's `package.json` an add in dependencies:

```
"ui": "*",
```

2. Import package as:

```
import { Button } from 'ui'
```

3. Go to monorepo's root and do `yarn`

Done!
