# China upstream union — 2026-11-23

The user explicitly requested merging all active rules from six upstream lists. This supersedes the prior selective import policy. The original 56 rules are retained verbatim, and every active upstream rule is present. Only identical rule lines are deduplicated; suffix-covered entries and overlapping IP ranges remain. Commented-out upstream rules are not activated. Sources were fetched directly from raw.githubusercontent.com (the GitHub mirror prefix changes transport, not the requested source).

This intentionally includes numeric DOMAIN-KEYWORD patterns, IP ranges, ASN 132203, top-level suffixes, USER-AGENT and PROCESS-NAME entries. They are preserved as routing choices, not certified as narrow product-only destinations. Shared Tencent/Alibaba infrastructure can route unrelated traffic through the same selected policy. A source rule is not proof of present ownership or necessity.

| Source | Active source lines | Newly added after earlier sources | Snapshot SHA-256 |
| --- | ---: | ---: | --- |
| [NobyDa / WeChat](https://raw.githubusercontent.com/NobyDa/Script/master/Surge/WeChat.list) | 341 | 318 | `f6ab694f5cbdd28294279ca58541bcb310e1b208d50314f94470cc05ba1ee99d` |
| [Coldvvater / WeChat](https://raw.githubusercontent.com/Coldvvater/Mononoke/refs/heads/master/Surge/Rules/WeChat.list) | 33 | 1 | `6f84eb140617a7335da7358f3eed6f475552e1925a0182e097ea5886b60a2086` |
| [blackmatrix7 / WeChat](https://raw.githubusercontent.com/blackmatrix7/ios_rule_script/master/rule/Surge/WeChat/WeChat.list) | 332 | 54 | `01e55617280a7b03db13397fcd2fe4bb3be559f728145fb1fbb054036d75d0bc` |
| [blackmatrix7 / AliPay](https://raw.githubusercontent.com/blackmatrix7/ios_rule_script/master/rule/Surge/AliPay/AliPay.list) | 21 | 13 | `23d7ca5404f4795d485b4ea700f45e1d94f2dbf0f2871eeca5298cfce81ff5be` |
| [blackmatrix7 / Alibaba](https://raw.githubusercontent.com/blackmatrix7/ios_rule_script/master/rule/Surge/Alibaba/Alibaba.list) | 58 | 58 | `3d605a61b5d0789ca3835c0a040f8d764dff1ec325ff9857af3720658a20e6de` |
| [blackmatrix7 / JingDong](https://raw.githubusercontent.com/blackmatrix7/ios_rule_script/master/rule/Surge/JingDong/JingDong.list) | 249 | 249 | `0b7a01784c5dfdb1a18d9051f4872c4078c6d5deb6a24f71bfe2bc06d96bb02a` |

## Validation

Combined rules: 749. Original baseline: 56/56 retained. All six source rule sets are subsets of the combined rule set. Type/field and IP parse checks passed; identical duplicates are absent. No Surge runtime, payment, login or call test was performed. USER-AGENT and process matching depend on platform and available metadata. The AI and overseas-bank files are unchanged.

Rule counts by type:

- DOMAIN: 13
- DOMAIN-KEYWORD: 233
- DOMAIN-SUFFIX: 319
- IP-ASN: 1
- IP-CIDR: 56
- IP-CIDR6: 124
- PROCESS-NAME: 1
- USER-AGENT: 2
