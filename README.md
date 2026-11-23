# My Rules

Personal Surge rule sets, maintained as small overrides alongside public rule sets.

| File | Purpose | Subscription |
| --- | --- | --- |
| `proxy.list` | Personal proxy overrides (initially empty) | [Raw](https://raw.githubusercontent.com/Kimcool/my-rules/main/proxy.list) |
| `direct.list` | Personal direct overrides (initially empty) | [Raw](https://raw.githubusercontent.com/Kimcool/my-rules/main/direct.list) |
| `ai.list` | AI services, grouped by provider (Claude first) | [Raw](https://raw.githubusercontent.com/Kimcool/my-rules/main/ai.list) |

## Use in Surge

Add the following lines to your existing `[Rule]` section, before broader public rules and `FINAL`. Replace `Proxy` and `AI` with existing policy group names in your profile.

```ini
RULE-SET,https://raw.githubusercontent.com/Kimcool/my-rules/main/direct.list,DIRECT
RULE-SET,https://raw.githubusercontent.com/Kimcool/my-rules/main/ai.list,AI
RULE-SET,https://raw.githubusercontent.com/Kimcool/my-rules/main/proxy.list,Proxy
```

The proxy and direct lists intentionally contain only comments until you add personal overrides. The AI list starts with user-supplied Claude domains and IP networks, organized into commented sections. It replaces the former `meta.list`; update existing subscriptions to `ai.list`. Domain ownership and completeness have not been independently verified. Shared support, verification and analytics domains can also route traffic from other products. IP rules use `no-resolve` to avoid triggering DNS resolution solely for matching these networks.

## Maintain

Edit the appropriate `.list` file on GitHub and commit to `main`, then refresh external rule sets in Surge. Remote content may be cached; changes are not necessarily immediate.

- `DOMAIN,example.com` matches that exact domain.
- `DOMAIN-SUFFIX,example.com` matches the domain and its subdomains.
- Use `#` for comments and keep one rule per line.
- Do not include a policy name, URL scheme, or URL path in domain entries.
- Avoid duplicate or conflicting entries across lists; the first matching rule wins.
- Keep credentials, node subscriptions, and private configuration out of this public repository.

Reference: [Surge rule sets](https://manual.nssurge.com/rules/ruleset.html).
