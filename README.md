# My Rules

Personal Surge rule sets, maintained as small overrides alongside public rule sets.

| File | Purpose | Subscription |
| --- | --- | --- |
| `proxy.list` | Personal proxy overrides (initially empty) | [Raw](https://raw.githubusercontent.com/Kimcool/my-rules/main/proxy.list) |
| `direct.list` | Personal direct overrides (initially empty) | [Raw](https://raw.githubusercontent.com/Kimcool/my-rules/main/direct.list) |
| `meta.list` | Facebook and Instagram starter domains | [Raw](https://raw.githubusercontent.com/Kimcool/my-rules/main/meta.list) |

## Use in Surge

Add the following lines to your existing `[Rule]` section, before broader public rules and `FINAL`. Replace `Proxy` and `🌐 meta` with existing policy group names in your profile.

```ini
RULE-SET,https://raw.githubusercontent.com/Kimcool/my-rules/main/direct.list,DIRECT
RULE-SET,https://raw.githubusercontent.com/Kimcool/my-rules/main/meta.list,🌐 meta
RULE-SET,https://raw.githubusercontent.com/Kimcool/my-rules/main/proxy.list,Proxy
```

The proxy and direct lists intentionally contain only comments until you add personal overrides. The Meta list is a starter list, not complete service coverage.

## Maintain

Edit the appropriate `.list` file on GitHub and commit to `main`, then refresh external rule sets in Surge. Remote content may be cached; changes are not necessarily immediate.

- `DOMAIN,example.com` matches that exact domain.
- `DOMAIN-SUFFIX,example.com` matches the domain and its subdomains.
- Use `#` for comments and keep one rule per line.
- Do not include a policy name, URL scheme, or URL path in domain entries.
- Avoid duplicate or conflicting entries across lists; the first matching rule wins.
- Keep credentials, node subscriptions, and private configuration out of this public repository.

Reference: [Surge rule sets](https://manual.nssurge.com/rules/ruleset.html).
