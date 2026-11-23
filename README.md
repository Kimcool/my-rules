# My Rules

Personal Surge rule sets. AI entries are grouped by provider, covering 16 provider sections including Chinese and international services. Official and community sources are mixed; see [review and limitations](REVIEW.md).

| File | Purpose |
| --- | --- |
| [ai.list](ai.list) | All 293 rules, including the full original Claude baseline, other providers, shared dependencies and IP ranges |
| [china.list](china.list) | 749 rules: WeChat, Alipay, Alibaba/Taobao, JD and existing services; suggested DIRECT |
| [outbank.list](outbank.list) | HSBC, Elephant Bank, ZA Bank and Wise; converted from yeahwu Bank.list |
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

china.list retains the original 56 rules and merges every active rule from the six user-selected WeChat, AliPay, Alibaba and JingDong lists. Only identical lines are deduplicated. See [source snapshots and validation](CHINA-REVIEW.md). Broad cloud networks, ASN, TLD suffixes, numeric domain keywords and process/User-Agent rules are intentionally retained; the policy can affect other Tencent/Alibaba services. This is a manual snapshot, not automatic upstream synchronization. No live-client login, payment or call test was performed. The AI and overseas-bank lists are unchanged.

## Overseas banking subscription

Converted from [yeahwu Bank.list](https://github.com/yeahwu/Rules-For-Quantumult-X/blob/main/Rules/Services/Bank.list), retaining every active rule and leaving its commented wildcard inactive. HOST becomes DOMAIN, HOST-SUFFIX becomes DOMAIN-SUFFIX, and the embedded Bank policy is removed. Upstream shared analytics, risk and support domains remain included and may match other apps. This is a manual snapshot, not automatic upstream synchronization.

Add to your existing `[Rule]` section before broader rules and FINAL. Replace `Bank` with your existing banking policy or chosen outbound policy; the repository does not select or create an outbound group.

```ini
RULE-SET,https://raw.githubusercontent.com/Kimcool/my-rules/main/outbank.list,Bank
```
