# OpenClash Qi Strategy Notes

This repository is a public template only. Do not commit real subscription URLs,
tokens, generated provider YAML files, or local `subs.txt` / `suss.txt` files.

## Current Routing Idea

The template keeps the Aethersailor/OpenClash split-routing structure and adds a
small set of explicit rules for services that are easy to miss when geosite data
lags behind.

- Keep `google-cn`, `cn`, and private networks direct for domestic traffic.
- Keep Aethersailor rule providers for custom direct/proxy and port rules.
- Keep AI traffic in dedicated policies instead of sending it through the catch-all.
- Keep Google Play Store traffic before `google-cn`, because mobile downloads may
  use Google CDN domains such as `dl.google.com` and `gvt*.com`.
- Prefer US, Japan, and Singapore groups for AI policies because account and API
  services are more sensitive to region quality than normal browsing.

## AI Services

The template still uses `GEOSITE,openai`, `GEOSITE,bing`, and
`GEOSITE,category-ai-!cn`, but adds explicit fallback domains for:

- Codex / OpenAI / ChatGPT / Sora
- GitHub Copilot and Microsoft Copilot
- Claude / Anthropic
- Gemini / AI Studio / NotebookLM / Jules / Stitch
- Pi / Inflection
- Hermes / Nous Research
- OpenRouter

These explicit rules are placed before the broad geosite AI rules.

## Google Play

The `🛒 Google Play` policy is placed before `GEOSITE,google-cn`.

Covered domains include:

- `play.google.com`
- `play.googleapis.com`
- `play-fe.googleapis.com`
- `android.clients.google.com`
- `play-lh.googleusercontent.com`
- `ggpht.com`
- `dl.google.com`
- `gvt1.com`
- `gvt2.com`
- `gvt3.com`

For phones, the router/DNS path still matters. If Play Store does not load after
importing this template, confirm the phone is using OpenClash DNS and clear stale
Play Store / Google Play Services cache.

## Safe Usage

Use the public remote config URL with your own subscription URL only in your
subconverter or OpenClash setup. Do not paste the generated URL into this repo if
it contains a token.

```text
https://raw.githubusercontent.com/qi-hey/openclash-Qi/main/cfg/Custom_Clash_Qi.ini
```
