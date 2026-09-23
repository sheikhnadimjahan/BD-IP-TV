# Banglar Darpan LIVE — rebuild notes

This package is a full working-copy rebuild based on the supplied project archive.

## Applied corrections

- Added root `vercel.json` for the existing Vite workspace build/output.
- Made the public viewer boot without a Clerk publishable key, so a missing auth environment variable no longer crashes the site.
- Kept Clerk sign-in/sign-up/admin behavior available when `VITE_CLERK_PUBLISHABLE_KEY` is configured.
- Removed the dependency on Clerk's internal `publishableKeyFromHost` helper in the app entry path.
- Hardened local lineup parsing and browser storage handling.
- Improved YouTube iframe startup reliability by enabling muted autoplay and passing the current origin.
- Made the signal clock dynamic instead of using a hard-coded time.
- Added responsive, fullscreen, accessibility, reduced-motion, touch, and focus polish.
- Kept the existing Banglar Darpan LIVE branding and the existing default YouTube report IDs unchanged.
- Clarified that the community test lane is browser-only preview; it does not upload or publish local files.
- Prevented the Replit runtime error overlay from being injected into production Vite builds.
- Added deployment notes for Vercel and the Clerk configuration boundary.

## Verification

A syntax-oriented TypeScript pass was run against the modified app/config files. The environment does not contain the project's installed npm/pnpm dependencies, and outbound npm registry access is unavailable here, so a real dependency install and production build could not be executed in this workspace.
