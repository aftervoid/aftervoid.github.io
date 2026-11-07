# Website fonts

This directory contains font binaries used by the website. The English homepage self-hosts all five families used by its typography system; external mirrors are retained as fallback routes. See [English typography and font delivery](../FONT-DELIVERY.md) for the delivery order and limitations.

## Font inventory

| Family | Files in this directory | Main use |
|---|---|---|
| **DM Sans** | `DMSans[opsz,wght].ttf` | English homepage body text, navigation, forms, and buttons |
| **Space Grotesk** | `SpaceGrotesk[wght].ttf` | English homepage headings and section titles |
| **Pixelify Sans** | `PixelifySans[wght].ttf` | Small decorative English UI accents |
| **Press Start 2P** | `PressStart2P-Regular.ttf` | Occasional retro display accents |
| **Inter** | `InterVariable.woff2` | Secondary English homepage fallback and English Royesh story interface |
| **Lora** | `Lora[wght].woff2` | English Royesh story prose |
| **Cormorant Garamond** | `CormorantGaramond-Light.woff2`, `CormorantGaramond-Regular.woff2`, `CormorantGaramond-Medium.woff2`, `CormorantGaramond-SemiBold.woff2`, `CormorantGaramond-Bold.woff2`, `CormorantGaramond-Italic.woff2` | English Royesh story display typography |
| **Cascadia Code** | `CascadiaCode.woff2` | Code samples and phonetic/IPA notation |
| **Rooyin** | `rooyin/RooyinFree-Regular.woff2`, `rooyin/RooyinFree-Bold.woff2` | Persian homepage interface and reading text |
| **Vazirmatn** | `Vazirmatn.woff2` | Retained Persian font asset and fallback use |

The English homepage uses DM Sans for readable text and controls, Space Grotesk for headings, Inter as a secondary fallback, and pixel fonts only for decorative accents. The English story has a separate editorial type system. Persian homepage text uses Rooyin.

## Licensing

The font families listed above are distributed under the **SIL Open Font License, Version 1.1 (OFL-1.1)** according to their accompanying upstream notices. Complete license texts are stored in [`../licenses/`](../licenses/).

For copyright notices, upstream project links, Reserved Font Name declarations, and redistribution notes, see [`../THIRD-PARTY-NOTICES.md`](../THIRD-PARTY-NOTICES.md). The license files—not this summary—contain the applicable legal terms.

## Updating a font

Before replacing, converting, subsetting, or modifying a font:

1. Identify the exact upstream project and version.
2. Read that version's copyright notice and complete license.
3. Check whether the upstream notice declares a **Reserved Font Name**.
4. Confirm that the intended file format and any conversion comply with the OFL and its FAQ.
5. Update this inventory, the matching file in `licenses/`, and the attribution in `THIRD-PARTY-NOTICES.md`.
6. Test the relevant pages, including fallback behavior and mobile layouts.

The automated workflow currently synchronizes license texts for Cormorant Garamond, Inter, Lora, Cascadia Code, and Vazirmatn only. It does not update font binaries and does not automatically check every font family in this directory. Review upstream notices manually when changing versions.

## Scope

Font licenses apply to the font software. They do not automatically license the website's source code, the Royesh story, illustrations, or other original content. See the repository's [license overview](../README.md#license-overview).