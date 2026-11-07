# Dogged Engineer

[doggedengineer.ca](https://doggedengineer.ca)

```sh
pnpm i
pnpm dev
```

Type-checking uses TypeScript `7.1.0-dev.20261107.1` and the official
`@astrojs/ts-content-mapper` integration. The `check` command generates Astro's
types, then runs `tsc` with `--runExternalCode` to enable the content mapper.
The compiler is a pinned prerelease. `@emnapi/runtime` is pinned to `1.11.3`
to match the mapper's WebAssembly dependencies.

## Caching

Cloudflare automatically caches static assets at its edge. `public/_headers`
sets browser caching for this deployment:

- HTML keeps the default `public, max-age=0, must-revalidate` behavior, with ETags.
- Astro's hashed `/_astro/` assets are cached for one year with `immutable`.
- Fonts are cached for one day because their URLs are not versioned.

If a font changes at the same URL, browsers may keep the previous file for up to
one day. Give changed fonts new URLs when an update must take effect immediately.
