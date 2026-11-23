# My Rules

Personal Surge rule sets. AI entries are grouped by provider, covering 16 provider sections including Chinese and international services. Official and community sources are mixed; see [review and limitations](REVIEW.md).

| File | Purpose |
| --- | --- |
| [ai.list](ai.list) | All 293 rules, including the full original Claude baseline, other providers, shared dependencies and IP ranges |
| [china.list](china.list) | WeChat/WeChat Pay, Alipay, Taobao/Tmall/Goofish and related resources; suggested DIRECT |
| [proxy.list](proxy.list) | Personal proxy overrides (initially empty) |
| [direct.list](direct.list) | Personal direct overrides (initially empty) |

## Subscribe

Add to your existing `[Rule]` section before broader rules and `FINAL`. Replace `AI` and `Proxy` with existing policy names. These are fragments, not a complete profile.

```ini
RULE-SET,https://raw.githubusercontent.com/Kimcool/my-rules/main/direct.list,DIRECT
RULE-SET,https://raw.githubusercontent.com/Kimcool/my-rules/main/proxy.list,Proxy
RULE-SET,https://raw.githubusercontent.com/Kimcool/my-rules/main/china.list,DIRECT
RULE-SET,https://raw.githubusercontent.com/Kimcool/my-rules/main/ai.list,AI
```

The single ai.list subscription includes shared dependencies and Claude IP rules. Shared dependencies also affect non-AI traffic. They can be required by a feature while already covered by your general routing policy. Domestic services in ai.list use the same chosen policy; put deliberate exceptions in direct.list first. Rule matching does not guarantee regional access, account eligibility, WebSocket or voice connectivity.

## Maintain

Edit a list and commit to main, then refresh external rule sets in Surge. Remote caching may delay updates. Keep one rule per line, with no policy component. DOMAIN matches an exact host; DOMAIN-SUFFIX includes the domain and its subdomains. Prefer exact hosts on shared platforms. Add a source comment and avoid suffix-covered duplicates. Never add credentials or private configuration.

The ai.list subscription URL is unchanged. The temporary optional-dependencies.list and optional-ips.list files have been merged into ai.list and removed; subscribe only to ai.list for AI routing. The former meta.list is no longer maintained. All 38 domain rules and 4 IP ranges from the original Claude list are retained explicitly. Research annotations do not authorize deleting or narrowing this user-maintained baseline; see REVIEW.md. No installed Surge profile is changed by editing this repository.

Reference: [Surge rule sets](https://manual.nssurge.com/rules/ruleset.html).

## China services scope

china.list is a separate subscription for the requested everyday services, not a complete mainland-China routing database. WeChat domains come from the linked community rule source; Alipay and shopping domains are supported by the official agreement and homepage resource inspection cited in the list. Shared Tencent/Alibaba resources also affect other products. No broad qq.com, aliyuncs.com or cloud IP/ASN rules are included. IP-only connections, voice/video calls, merchant sites and third-party mini-program backends may need additional observed rules. No real-device login, payment or call test was performed. Existing AI rules are unchanged.
