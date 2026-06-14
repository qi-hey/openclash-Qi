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

## Subconverter remote config

Use this URL as the remote config / `config` parameter:

```text
https://raw.githubusercontent.com/qi-hey/openclash-Qi/main/cfg/Custom_Clash_Qi.ini
```

The config references this base YAML:

```text
https://raw.githubusercontent.com/qi-hey/openclash-Qi/main/base/openclash-meta-gateway.yaml
```

## Example

Replace `YOUR_SUB_URL` with your subscription URL:

```text
https://subconverter.example/sub?target=clash&url=YOUR_SUB_URL&config=https%3A%2F%2Fraw.githubusercontent.com%2Fqi-hey%2Fopenclash-Qi%2Fmain%2Fcfg%2FCustom_Clash_Qi.ini
```

After conversion, import the generated YAML into OpenClash and use the Meta /
Mihomo kernel.

## Notes

The original GitHub raw URL for Aethersailor's template may return 404 in some
environments, so this fork keeps a working template and points rule providers to
`api.asailor.org`.
