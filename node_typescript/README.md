# node_typescript

Node 16 + TypeScript

## Setup

```sh
yarn add --dev @types/node typescript ts-node @tsconfig/node16
```

```sh
yarn add --dev eslint prettier eslint-config-prettier @types/eslint @typescript-eslint/eslint-plugin @typescript-eslint/parser
```

## tsconfig.json

```json
{
  "compileOnSave": false,
  "compilerOptions": {
    "baseUrl": ".",
    "outDir": "./dist",
    "rootDir": "./src",
    "typeRoots": ["./node_modules/@types"],
    "downlevelIteration": true,
    "emitDecoratorMetadata": true,
    "esModuleInterop": true,
    "experimentalDecorators": true,
    "forceConsistentCasingInFileNames": true,
    "importHelpers": true,
    "jsx": "react",
    "moduleResolution": "node",
    "noImplicitAny": false,
    "resolveJsonModule": true,
    "sourceMap": true,
    "strict": true,
    "skipLibCheck": true,
    "module": "Node16",
    "target": "ESNext"
  },
  "exclude": ["**/*.spec.ts", "node_modules"]
}
```

## .eslintrc.js

```js
module.exports = {
  root: true,
  env: {
    es6: true,
    node: true,
  },
  extends: [
    'eslint:recommended',
    'plugin:@typescript-eslint/eslint-recommended',
    'prettier',
    'prettier/@typescript-eslint',
  ],
  parser: '@typescript-eslint/parser',
  parserOptions: {
    ecmaVersion: 2018,
    sourceType: 'module',
  },
  plugins: ['@typescript-eslint'],
  rules: {
    '@typescript-eslint/no-unused-vars': [
      'error',
      {
        argsIgnorePattern: '^_',
      },
    ],
    'no-unused-vars': 'off',
    radix: 'error',
  },
};
```

## .prettierrc.json5

```json
{
  overrides: [
    {
      files: ["*.js", "*.ts", "*.tsx"],
      options: {
        singleQuote: true,
      },
    },
  ],
}
```
