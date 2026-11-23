# My Rules

Personal Surge rule sets. AI entries are grouped by provider, covering 16 provider sections including Chinese and international services. Official and community sources are mixed; see [review and limitations](REVIEW.md).

| File | Purpose |
| --- | --- |
| [ai.list](ai.list) | Service-scoped AI domains, including dedicated hosts on shared clouds |
| [optional-dependencies.list](optional-dependencies.list) | Shared login, verification, support, download and telemetry services; opt in deliberately |
| [optional-ips.list](optional-ips.list) | Official Claude API/Console inbound IP ranges; opt in if needed |
| [proxy.list](proxy.list) | Personal proxy overrides (initially empty) |
| [direct.list](direct.list) | Personal direct overrides (initially empty) |

## Subscribe

Add to your existing `[Rule]` section before broader rules and `FINAL`. Replace `AI` and `Proxy` with existing policy names. These are fragments, not a complete profile.

```ini
RULE-SET,https://raw.githubusercontent.com/Kimcool/my-rules/main/direct.list,DIRECT
RULE-SET,https://raw.githubusercontent.com/Kimcool/my-rules/main/proxy.list,Proxy
RULE-SET,https://raw.githubusercontent.com/Kimcool/my-rules/main/ai.list,AI
```

Optional additions, after the main domain rules:

```ini
RULE-SET,https://raw.githubusercontent.com/Kimcool/my-rules/main/optional-dependencies.list,AI
RULE-SET,https://raw.githubusercontent.com/Kimcool/my-rules/main/optional-ips.list,AI
```

Shared dependencies also affect non-AI traffic. Review the file before subscribing wholesale, or copy only needed rules into personal overrides. They can be required by a feature while already covered by your general routing policy. Domestic services in ai.list use the same chosen policy; put deliberate exceptions in direct.list first. Rule matching does not guarantee regional access, account eligibility, WebSocket or voice connectivity.

## Maintain

Edit a list and commit to main, then refresh external rule sets in Surge. Remote caching may delay updates. Keep one rule per line, with no policy component. DOMAIN matches an exact host; DOMAIN-SUFFIX includes the domain and its subdomains. Prefer exact hosts on shared platforms. Add a source comment and avoid suffix-covered duplicates. Never add credentials or private configuration.

The ai.list subscription URL is unchanged. The former meta.list is no longer maintained. The previous Claude-only list was replaced; unverified aliases and broad IP ranges are explained in REVIEW.md. No installed Surge profile is changed by editing this repository.

Reference: [Surge rule sets](https://manual.nssurge.com/rules/ruleset.html).
