# Dogged Engineer

Dogged Engineer landing page

Requires Node.js 22.23.4 or newer. The package manager is pinned to pnpm 12.18.0.

```sh
pnpm install
pnpm dev
```

The development server runs at http://localhost:4321.

Edit `src/pages/index.astro` to build the home page. Place static assets in `public/`.

```sh
pnpm check    # Type-check TypeScript and Astro files
pnpm build    # Generate the production site in dist/
pnpm preview  # Preview the production build locally
```

Type-checking uses TypeScript `7.1.0-dev.20261107.1` and the official
`@astrojs/ts-content-mapper` integration. The `check` command generates Astro's
types, then runs `tsc` with `--runExternalCode` to enable the content mapper.
The compiler is a pinned prerelease. `@emnapi/runtime` is pinned to `1.11.3`
to match the mapper's WebAssembly dependencies.
