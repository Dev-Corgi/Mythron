<!-- bmad:context -->
<!-- Verified 2026-10-28 against 2843f2400854136598631288c2e8dfb8f5173de7. Managed by bmad-project-context; edits inside this block are replaced on refresh. Keep anything you want preserved outside the markers. -->

## Mythron

Mythron currently uses imported OpenDuelyst code: a Backbone/Marionette client and Node/CoffeeScript services. `docs/ARCHITECTURE.md` explains the existing service boundaries. `docs/QUICKSTART.md` covers local setup, and `docs/CONTRIBUTING.md` covers tests, pull requests, and versioning.

## Running and verifying

- Use Node 24 and Corepack-managed Yarn 4.9.2; CI uses Node 24 and `package.json` pins Yarn 4.9.2.
- Before `yarn build`, run `yarn tsc:chroma-js` and set `FIREBASE_URL` to a URL ending in `firebaseio.com/`; the build rejects missing or differently ending values.
- Start Redis and Postgres and run migrations before backend integration tests. CI runs only `test:integration:misc`, so run other relevant integration suites when changing them.
- Set `NODE_ENV` when running `yarn migrate:latest` outside Docker Compose; `server/knexfile.js` exits without it.

<!-- /bmad:context -->
