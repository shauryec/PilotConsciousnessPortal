# Pilot Consciousness Portal

This repository is the portal's sole hosting source. It does not use ChatGPT Sites.

## Production hosting

GitHub Pages serves the built portal from the repository root:

- Branch: `main`
- Folder: `/(root)`
- Custom domain: `portal.pilotconsciousness.com`

The `CNAME` file keeps that domain associated with this repository. Configure the DNS record for `portal` as a CNAME to `shauryec.github.io`.

## Source

The portal is a Vite/React application backed by Supabase. Before a source change is published, build it with Vite using base `/`, then replace the root `index.html` and `assets/` with the generated production files. The root is intentionally the deployable version so Pages serves the portal at the domain root, not a fragile `/portal` subpath.

The app must retain the current product rules:
- lessons are displayed as `Lesson 1`, `Lesson 2`, etc.
- Flight, Ground, Sim, and Solo are activity types, not lesson titles.
- course completion is based on completed lessons, not ACS-task percentage.
