# RuView — Vercel Deployment

This package is the **static web UI** of RuView prepared for Vercel.

## Important

The original repository contains Python/Rust services and hardware/CSI integrations that cannot run as a normal Vercel static frontend. This deployment therefore runs the UI in **clearly labelled client-side simulation mode** on `*.vercel.app`.

It does **not** turn a laptop's normal Wi-Fi RSSI into CSI, and it does not claim simulated data is real RF measurement.

## Deploy

1. Create/import a Git repository containing this folder.
2. In Vercel, choose **New Project** and import the repository.
3. Framework: **Vite** (or Other).
4. Build command: `npm run build`
5. Output directory: `dist`
6. Install command: `npm install`
7. Deploy.

No environment variables are required for the simulation demo.

## Simulation / real backend switch

- Vercel automatically enables the client simulator.
- `https://YOUR-DOMAIN.vercel.app/?simulate=1` explicitly enables simulation.
- `?simulate=0` disables the client simulator so a compatible real backend can be connected.

## Local

```bash
npm install
npm run dev
```

Then open the Vite URL.

## Original backend

For real CSI/ESP32 sensing, keep using the original RuView Python/Rust/hardware services outside Vercel and point the frontend at an appropriate backend. Vercel is only hosting this frontend package.
