# FallPhone

**Sovereign phone setup toolkit.** Turn a fresh Pixel or PinePhone into your sovereign phone in about thirty minutes.

Live at **https://sjgant80-hub.github.io/fallphone/**

Part of the [AI-Native Solutions](https://ai-nativesolutions.com) estate.

---

## What is a sovereign phone?

A phone where **you** decide what runs, what talks to the network, what data leaves the device, and which company (if any) sees your identity. Not a paranoid burner — a normal daily driver, with the default flipped from *rented* to *owned*.

Concretely that usually means:

- **Hardware you can flash** — a Pixel 6-9, a PinePhone Pro, or a device that ships with a de-Googled OS.
- **An OS you can audit** — GrapheneOS (hardened Android), /e/OS, or postmarketOS.
- **Your identity, not their identity** — a keypair you generated, not a Google or Apple account.
- **Apps that live on the open web** — Progressive Web Apps you install from the browser, not from a store that can revoke them.

None of this is exotic. It's just less common because the mainstream phone experience has been optimised around convenience-for-them rather than sovereignty-for-you.

## Why it matters

Not a manifesto — just the practical stuff:

- **You own the keys.** When your identity is a keypair you hold rather than a login you rent, no company can lock you out, no policy change can strand your data, and no state can flip a switch on you at the platform level.
- **Fewer default trackers.** GrapheneOS ships with location off, no Google Play by default, and a hardened browser. That's not paranoia — that's the sane default position for a general-purpose computer that lives in your pocket.
- **Portability.** The estate PWAs work identically on your desktop and your phone. Your data lives in IndexedDB on each device and syncs peer-to-peer via FallSync. Move to another phone tomorrow and the whole set-up transfers in one QR scan.
- **Digital rights.** A phone that doesn't phone home by default is a phone whose posture matches what most privacy law was written to protect. If that matters to you — or to the people you work with — this is the base layer.

## How to use it

Open [sjgant80-hub.github.io/fallphone](https://sjgant80-hub.github.io/fallphone/) on your **desktop**. Walk the five steps:

1. **Pick the hardware.** Comparison table with UK/EU prices. The 90% pick is a used Pixel 7a for around £220.
2. **Flash GrapheneOS.** Direct link to the official web installer. Runs from any Chromium browser over USB. Fifteen minutes.
3. **Transfer your FallID.** Enter a passphrase; FallPhone encrypts your keypair and shows a QR. Scan on the phone. Same identity, both devices.
4. **Install the estate.** Pulls the FallHarbor manifest, shows every shipped tool with one-tap install buttons.
5. **Verify the posture.** Six-item checklist — location off, modem sandboxed, Vanadium default, FallShell installed, DID matches. Green ticks as you go.

Your progress is saved to localStorage so you can come back to it.

## What runs where

FallPhone itself is a **static HTML page**. No backend. No account. All state (which step you're on, which PWAs you've marked installed, checklist ticks) lives in your browser's localStorage. All crypto (AES-GCM encryption for the QR payload) runs in Web Crypto in the browser.

- QR encoder is inline vanilla JS (no external library)
- Fallback list of estate PWAs ships baked in — the live FallHarbor manifest overrides it when reachable
- Works offline after first load (service worker)

## Uses these estate primitives

- **FallID** · [sjgant80-hub.github.io/fallid](https://sjgant80-hub.github.io/fallid/) · sovereign identity keypair
- **FallSync** · [sjgant80-hub.github.io/fallsync](https://sjgant80-hub.github.io/fallsync/) · multi-device state sync
- **FallShell** · [sjgant80-hub.github.io/fallshell](https://sjgant80-hub.github.io/fallshell/) · estate portal
- **FallHarbor** · [sjgant80-hub.github.io/fallharbor](https://sjgant80-hub.github.io/fallharbor/) · tool manifest

## License

MIT. Fork it, ship it, rename it — the recipe is the point, not the branding.

---

◊ AI-Native Solutions · 2026
