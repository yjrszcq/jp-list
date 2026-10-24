# JP Site 分流规则

日本常见网站及服务的分流规则。

## Rule Provider

> 以下两种仅为不同的表示方式，作用相同，二选一即可

```yaml
jp-site: {type: http, format: yaml, behavior: classical, url: "https://raw.githubusercontent.com/yjrszcq/jp-site-list/refs/heads/main/jp-site.yaml", path: ./ruleset/jp-site.yaml, interval: 86400}
```

```yaml
jp-site:
  type: http
  format: yaml
  behavior: classical
  url: "https://raw.githubusercontent.com/yjrszcq/jp-site-list/refs/heads/main/jp-site.yaml"
  path: ./ruleset/jp-site.yaml
  interval: 86400
```

## Rules

> 假设你的 `proxy-groups` 中对日本网站分流的代理组名为 `JP`

```yaml
rules:
  # JP Site
  - RULE-SET,jp-site,JP
```

## LIST

同时提供 LIST 格式规则：

```text
https://raw.githubusercontent.com/yjrszcq/jp-site-list/refs/heads/main/jp-site.list
```

## 说明

本规则主要收录常见日本网站及日本本土服务，包括但不限于：

- Yahoo! JAPAN
- Rakuten
- Amazon Japan
- Mercari
- BitCash
- DMM / FANZA
- Pixiv
- NicoNico
- ABEMA
- TVer
- NHK
- DLsite
- BOOK☆WALKER
- BOOTH
- 日本电商及通信服务

规则不会直接匹配全部 `.jp` 域名，而是以具体网站及服务域名为主，避免不必要的日本节点分流。
