# openclash-Qi

OpenClash / Mihomo gateway template based on Aethersailor Custom_OpenClash_Rules.

This repo provides a subconverter remote config that adds the gateway-oriented
OpenClash settings we use locally:

- `mixed-port: 7890`
- `redir-port: 7892`
- `tproxy-port: 7895`
- `tun` gateway mode
- fake-ip DNS with AI/OpenAI/Claude/Google DNS policy through `🚀 手动选择`
- maintained Aethersailor rule-provider URLs through `api.asailor.org`
- country-level automatic node groups, with `♻️ 自动选择` acting as a country
  entry selector instead of one mixed all-node latency pool
- explicit AI service rules for Codex, ChatGPT, Claude, Gemini, Pi, Hermes/Nous,
  Copilot, and OpenRouter
- a dedicated `🛒 Google Play` policy before `google-cn` so mobile Play Store
  downloads are less likely to be sent direct by mistake

This repository is public. It intentionally does not include subscription URLs,
tokens, generated provider YAML files, or local subscription text files.

## Subconverter remote config

Use this URL as the remote config / `config` parameter:

```text
https://raw.githubusercontent.com/qi-hey/openclash-Qi/main/cfg/Custom_Clash_Qi.ini
```

The config references this base YAML:

```text
https://raw.githubusercontent.com/qi-hey/openclash-Qi/main/base/openclash-meta-gateway.yaml
```

## Remote Config URL

Use this as the remote config / `config` URL in your converter:

```text
https://raw.githubusercontent.com/qi-hey/openclash-Qi/main/cfg/Custom_Clash_Qi.ini
```

Keep your real subscription URL only in your local converter or OpenClash setup.
After conversion, import the generated YAML into OpenClash and use the Meta /
Mihomo kernel.

`♻️ 自动选择` now points to country/region auto groups such as `🇯🇵 日本节点`,
`🇸🇬 新加坡节点`, and `🇺🇸 美国节点`. Each country group still uses `url-test`
with `https://cp.cloudflare.com/generate_204`, `interval: 300`, and
`tolerance: 50`, so nodes are automatically selected inside that region instead
of mixing every country into one Smart group.

## AI And Google Play Notes

The template keeps the original OpenClash/Aethersailor rule structure, then adds
explicit fallback domains before broad geosite rules:

- `🤖 ChatGPT`: OpenAI, ChatGPT, Codex-adjacent OpenAI assets, Sora
- `🤖 Copilot`: GitHub Copilot and Microsoft Copilot
- `🤖 AI服务`: Claude/Anthropic, Gemini/AI Studio, Pi/Inflection,
  Hermes/Nous, OpenRouter
- `🛒 Google Play`: Play Store API, app assets, and Google download CDN domains

For the implementation notes and the no-token publishing rule, see
[`docs/strategy-notes.md`](docs/strategy-notes.md).

## Notes

The original GitHub raw URL for Aethersailor's template may return 404 in some
environments, so this fork keeps a working template and points rule providers to
`api.asailor.org`.
