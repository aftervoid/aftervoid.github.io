# English typography and font delivery

The English homepage now uses a clear type hierarchy:

| Role | Primary family |
|---|---|
| Body copy, navigation, forms, buttons | **DM Sans** (variable, 100–1000) |
| Main headings and section titles | **Space Grotesk** (variable, 300–700) |
| Secondary UI fallback | **Inter** (variable, 100–900) |
| Small pixel-art accents | **Pixelify Sans** (400–700) |
| Occasional retro display accent | **Press Start 2P** (400) |

Pixelify Sans and Press Start 2P are no longer the default reading or heading faces. Their distinctive pixel shapes are retained for small decorative details; long paragraphs and large headings use more readable families.

## Locally hosted files

- `fonts/DMSans[opsz,wght].ttf` — DM Sans variable font.
- `fonts/SpaceGrotesk[wght].ttf` — Space Grotesk variable font.
- `fonts/InterVariable.woff2` — Inter variable font.
- `fonts/PixelifySans[wght].ttf` — Pixelify Sans variable font.
- `fonts/PressStart2P-Regular.ttf` — Press Start 2P regular.

The DM Sans and Space Grotesk binaries were copied from the official `google/fonts` repository. Their complete upstream OFL texts are included in `licenses/DM-Sans-OFL.txt` and `licenses/Space-Grotesk-OFL.txt`.

## Delivery and fallback routes

The relevant `@font-face` rules try the same-origin GitHub Pages file first, then repository mirrors on jsDelivr, Fastly jsDelivr, Gcore jsDelivr, raw.githack, and finally the official Google Fonts raw file. This makes the self-hosted file the normal path while preserving external recovery paths.

Additional family-level choices are available through Google Fonts CSS, Bunny Fonts (added if the Google Fonts stylesheet itself errors), Fontsource CSS, a locally installed copy of the family, and finally system fonts such as Segoe UI, Arial, or generic sans-serif.

Provider caveats matter: Fastly and Gcore are alternate jsDelivr endpoints, not wholly independent font sources. Fontsource's CDN is also jsDelivr-backed. raw.githack and raw.githubusercontent.com serve repository/upstream files, so these are delivery routes rather than independent font publishers.

A comma-separated `src` list tries another resource when a font resource is unusable. Separately loaded stylesheets are not a perfectly serialized failover chain: they can be requested independently, and a stylesheet `error` event does not reveal every failed font file referenced from a stylesheet.

## On-page diagnostics

The English page includes an on-demand **Typography diagnostics · Live font status** panel. It uses the browser Font Loading API to test the declared faces and Resource Timing to display a matching URL or host when the browser exposes it. Results are generated locally in the visitor's browser and are not uploaded.

The panel cannot reliably name the exact operating-system font chosen for a generic fallback. Browser caching and cross-origin timing restrictions can hide URLs or response codes. The test uses one Latin sample; it does not validate every glyph, weight, language, browser, or device.

## Performance and maintenance

- `font-display: swap` keeps text visible while a webfont loads.
- Local font files are the primary source, reducing runtime dependency on third-party services.
- Do not preload every family. If performance measurements justify it, preload only the critical face used above the fold.
- Keep each font binary with its full license text and attribution.
- Re-test the English homepage at desktop and mobile widths after changing typography.

## Upstream projects and references

- [Google Fonts repository guide](https://googlefonts.github.io/gf-guide/googlefonts.html)
- [Google Fonts repository](https://github.com/google/fonts)
- [DM Sans upstream project](https://github.com/googlefonts/dm-fonts)
- [Space Grotesk upstream project](https://github.com/floriankarsten/space-grotesk)
- [Inter upstream project](https://github.com/rsms/inter)
- [Pixelify Sans upstream project](https://github.com/eifetx/Pixelify-Sans)
- [Press Start 2P upstream project](https://github.com/google/fonts/tree/main/ofl/pressstart2p)
- [Fontsource CDN documentation](https://fontsource.org/docs/getting-started/cdn)
- [SIL Open Font License 1.1](https://openfontlicense.org/)

For exact attribution and legal terms, see `THIRD-PARTY-NOTICES.md` and the matching files in `licenses/`.