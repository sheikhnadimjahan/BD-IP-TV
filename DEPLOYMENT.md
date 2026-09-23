# Banglar Darpan LIVE — deployment notes

## Web app

The production viewer is `artifacts/banglar-darpan-live`.

The root `vercel.json` is configured for the Vite workspace:

- Install: `pnpm install --frozen-lockfile`
- Build: `pnpm --filter @workspace/banglar-darpan-live run build`
- Output: `artifacts/banglar-darpan-live/dist/public`

## Authentication

The public viewer works without Clerk configuration.

Set `VITE_CLERK_PUBLISHABLE_KEY` in the Vercel project to enable sign-in, sign-up, user portal, and the authenticated admin route. `VITE_CLERK_PROXY_URL` is optional when a Clerk proxy is configured.

## Important upload/safety boundary

The current community/test lane is intentionally browser-only. Local files are previewed with `URL.createObjectURL` and are not uploaded or published by this frontend.

Real public uploads require a server-side ingestion/moderation pipeline before publication (file validation, malware/content checks, storage controls, rate limiting, and moderation policy enforcement). Frontend checks alone must not be treated as publication safety controls.

## Branding and source lineup

The existing Banglar Darpan LIVE branding and the existing default YouTube report IDs are preserved in `src/App.tsx`.
