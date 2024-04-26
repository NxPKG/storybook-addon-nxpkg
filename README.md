# Storybook Addon NxPkg
Create a one-click Pull Request environment right from your component

## Installation

yarn:
```bash
yarn add --dev @nx-pkg/storybook-addon-nxpkg
```

npm:
```bash
npm install @nx-pkg/storybook-addon-nxpkg --save-dev
```

pnpm:
```bash
pnpm add --save-dev @nx-pkg/storybook-addon-nxpkg
```

## Usage

Add the following to your `.storybook/main.ts` (or `.storybook/main.js`) exports:

```typescript
export default {
  addons: ['@nx-pkg/storybook-addon-nxpkg'],
};
```

Configure the repository URL in the `.storybook/preview.ts` (or `.storybook/preview.js`):
```typescript
export default {
  parameters: {
    repositoryUrl: 'https://github.com/[username]/[reponame]'
  },
};
```

In your story files set the file path for the specific story, for instance:
```typescript
export const Primary: Story = {
  args: {/* ... */},
  parameters: {
    filePath: 'src/stories/Button.tsx'
  }
};
```

If your components are placed in multiple repositories, you can also define the repository URL per the specific story:
```typescript
export const Primary: Story = {
  args: {/* ... */},
  parameters: {
    filePath: 'src/stories/Button.tsx',
    repositoryUrl: 'https://github.com/[username]/[reponame]'
  }
};
```


## Development scripts

- `yarn start` runs babel in watch mode and starts Storybook
- `yarn build` build and package your addon code

## Addon icon

(for Storybook [integration catalog](https://storybook.js.org/integrations))

![icon](https://github.com/nxpkg/storybook-addon-nxpkg/assets/1511906/d8b5c029-8633-4d16-8a9e-5d5fe8456aeb)
