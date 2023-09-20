# Bun package manager does not work with Astro Image component

The bug causing this issue: https://github.com/lovell/sharp/issues/3779

Temporary workaround for this issue: https://github.com/astro-community/AstroCompress/issues/193#issuecomment-1726428853

## This repo

This repo was created on 2023-09-19 by running `npm create astro@latest` with the following choices (though I don't think the choices matter all that much):

- Include sample files
- Install dependencies: Yes
- Typescript: No
- New Git repo: No

## Run the code successfully with node:

```bash
git clone https://github.com/0livare/astro-image-with-bun.git
git checkout node-works
npm install
npm run build
# Build success
```

## Then reproduce the problem with bun as a package manager

```bash
rm package-lock.json
rm -rf node_modules
bun install
bun run build
# Build fails: Could not find Sharp. Please install Sharp (`sharp`) manually
```

You can try to follow its directions:

```bash
bun add sharp
bun run build
# Build STILL fails: Could not find Sharp. Please install Sharp (`sharp`) manually
```
