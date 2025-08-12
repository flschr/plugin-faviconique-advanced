# Faviconique+

**Turn a single emoji into a cross‑browser favicon – no image export, no build steps.**

Faviconique+ is a Micro.blog plug‑in that takes one emoji and serves it as PNG favicons via **EmojiCDN**. It also provides an Apple touch icon and a configurable browser UI color. Works in Safari, Chrome, Firefox, Edge — **no local image generation** needed.

> Credits: Inspired by the original [Faviconique](https://micro.blog/account/plugins/view/141) by Sven Dahlstrand. This plug‑in focuses on emoji-only favicons via a CDN and adds a few Micro.blog‑specific quality‑of‑life options.

---

## Features

- 🦄 **Emoji → favicon (PNG via CDN)**
  - Styles: **Apple**, **Twitter (Twemoji)**, **Facebook**, **Google**
- 📐 **Multiple sizes out of the box**
  - 16×16, 32×32, 48×48, 96×96, 192×192, 512×512
  - Plus **Apple touch icon** 180×180
- 📱 **Add to Home Screen**
  - Web App Manifest + optional iOS meta tags for app‑like launch
- 🚀 **Fast loading**
  - `preconnect` + `dns-prefetch` to EmojiCDN
  - Cache‑buster on URLs to avoid stale favicons
- 🏷️ **Configurable names** for home‑screen/app surfaces
  - Sets `apple-mobile-web-app-title` and `application-name`
- 🎨 **Theme color** for browser UI (Android/desktop browsers, Windows tiles)
  - Sets `theme-color` and `msapplication-TileColor`
- 🔧 **Zero local processing** – everything via CDN

---

## Configure

Fields in **Plugins → Faviconique+ → Settings**:

- **Emoji (only one)** – e.g. `🌱` *(required)*
- **Emoji style** – `apple`, `twitter`, `facebook`, or `google` *(required)*
- **Home screen title (optional)** – overrides the saved shortcut/app name
- **Theme color for browser UI** – used for `theme-color` and Windows tiles
- **Web app display (standalone or browser)** – choose `standalone` for an app‑like window or `browser` for a normal tab

> Tip: Placeholders in the UI are **not** saved values. Enter your own values and click **Update Settings**.

---

## Add to Home Screen

Once configured, visit your site on a mobile browser and use **Add to Home Screen**. The generated `manifest.webmanifest` and optional iOS meta tags launch in your chosen display mode with the selected emoji icon and theme color.

---

## How it works

- The plug‑in builds favicon URLs like:
  ```
  https://emojicdn.elk.sh/<emoji>?style=<style>&size=<N>&v=<timestamp>
  ```
- Browsers receive raster PNGs for each declared size. Safari gets a standard Apple touch icon (180×180).
- The CDN host is fixed to **emojicdn.elk.sh** for simplicity and reliability.

---

## License & credits

- © Contributors of Faviconique+. Credits to [Sven Dahlstrand](https://dahlstrand.net/) for the original Faviconique idea and assets.
- Emoji rendering provided by **EmojiCDN (elk.sh)**.
