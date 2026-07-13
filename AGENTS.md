# Fuwari — Astro static blog

## Commands

```sh
pnpm dev               # dev server at localhost:4321
pnpm build             # astro build + pagefind index (output: dist/)
pnpm preview           # preview built site
pnpm check             # astro check (type-check Astro files)
pnpm type-check        # tsc --noEmit --isolatedDeclarations
pnpm format            # biome format --write ./src
pnpm lint              # biome check --write ./src
pnpm new-post <name>   # creates src/content/posts/<name>.md with frontmatter
```

## Essentials

- **Package manager**: pnpm only (enforced via `only-allow` + `.npmrc`).
- **Lint/Format**: Biome (not ESLint/Prettier). Indent: tabs. Quotes: double.
- **Type check**: both `pnpm check` (Astro check) and `pnpm type-check` (tsc) are needed — they catch different issues.
- **Biome caveat**: CSS files are excluded. Some rules (`useConst`, `useImportType`, `noUnusedVariables`, `noUnusedImports`) are disabled for `.svelte`, `.astro`, `.vue`.
- **Config file**: `src/config.ts` — site title, theme, nav, profile, license, Expressive Code themes. Edit this to customize the blog.
- **Posts**: markdown/MDX in `src/content/posts/`. Frontmatter fields defined in `src/content.config.ts`.
- **Spec pages**: markdown/MDX in `src/content/spec/` (about, friends, etc.).
- **Path aliases** (from tsconfig): `@components/*`, `@assets/*`, `@utils/*`, `@i18n/*`, `@layouts/*`, `@/*` → `src/*`.
- **Build output**: `dist/` (gitignored). Generated types in `.astro/` (gitignored).
- **Deploy targets**: Vercel (`vercel.json` — empty defaults), Cloudflare Pages (`wrangler.jsonc`), GitHub Pages (`.github/workflows/astro.yml`).

## Architecture

- **Framework**: Astro 6 + Tailwind CSS 4 (via `@tailwindcss/vite`) + Svelte 5 (for interactive islands).
- **Page transitions**: swup (Astro integration), container IDs: `main`, `#toc`.
- **Search**: Pagefind (runs as post-build step in `pnpm build`).
- **Markdown pipeline**: remark (math, reading-time, excerpt, admonitions→directives, sectionize) → rehype (KaTeX, slug, autolink headings, custom components for GitHub/Codeberg cards, admonitions).
- **Code blocks**: Expressive Code with custom plugins (language badge, copy button, collapsible sections, line numbers).
- **Icons**: astro-icon with iconify sets (`mdi`, `fa6-brands`, `fa6-regular`, `fa6-solid`, `simple-icons`).
- **Check CI**: `pnpm check && pnpm format` before PR (per CONTRIBUTING.md).

## Gotchas

- `pnpm build` runs **both** `astro build` and `pagefind`. The `pagefind` step will fail if `dist/` is missing or empty — always use `pnpm build`, never just `astro build`.
- Biome `vcs.enabled` is `false` — it doesn't respect `.gitignore`. Files to ignore are listed in `biome.json`'s `files.includes`.
- Vite suppresses warnings about files that are both dynamically and statically imported.
- Post frontmatter includes `prevTitle`/`prevSlug`/`nextTitle`/`nextSlug` for internal use — don't edit those manually.
- The `lang` field in post frontmatter overrides the site language from `config.ts` for individual posts.
- The `.pages.yml` is empty (Cloudflare Pages config placeholder).
