# Rule review — 2026-11-23

## Evidence boundary

The six supplied research files were inputs, not independently reproduced research. Their X search counts, fetch dates, ownership claims and coverage ratings are not certified here. Community-derived entries remain candidates for practical routing, not guarantees of official ownership or completeness. No client capture or live login/upload/voice test was performed.

Official pages independently checked:

- [Claude Code networking](https://code.claude.com/docs/en/network-config)
- [Claude inbound and outbound addresses](https://platform.claude.com/docs/en/api/ip-addresses)
- [ChatGPT network recommendations](https://help.openai.com/en/articles/9247338-network-recommendations-for-chatgpt-errors-on-web-and-apps)
- [GitHub Copilot allowlist](https://docs.github.com/en/copilot/reference/copilot-allowlist-reference)
- [Cursor sign-in domains](https://cursor.com/help/troubleshooting/sign-in-domains)
- [Alibaba Model Studio overview](https://help.aliyun.com/zh/model-studio/what-is-model-studio)
- [Current ai.com website](https://ai.com/)

## Corrections

- Removed ai.com from OpenAI: its current website describes its own agent platform, not an OpenAI entry point.
- Moved Copilot-specific Web PubSub and report hosts to the main list, verified against GitHub. A dedicated hostname on a shared cloud is not equivalent to a shared hostname.
- Applied that same distinction to community-listed Perplexity upload/media and Cursor binary hosts; these remain community evidence.
- Moved generic Bing resource/API hosts to optional dependencies. Removed exact duplicates and suffix-covered entries across both files.
- Added the Beijing workspace-specific Model Studio API suffix documented by Alibaba. Other regions require separately confirmed endpoints.
- Corrected the OpenAI Azure/CDN comment: the checked ChatGPT article does not list those hosts; they remain community-derived candidates.
- Kept Cursor's new sign-in suffix: its official page explicitly recommends it, including related authentication hosts.
- Replaced the old IP set with a separate opt-in list: 160.79.104.0/23, 153.61.224.0/22 and 2607:6bc0::/48 are documented inbound addresses. 160.79.104.0/21 and 153.61.208.0/20 are documented OUTBOUND source ranges, not the client destination list. Removed unsubstantiated 34.8.0.0/16. This corrects the supplied report's claim that the /20 was not in visible documentation.

## Deferred and excluded

Unconfirmed Claude aliases from the previous list are not active: claude.app, claude.dev, claude.new, claude.site, claudeacademy.com, claudemcpclient.com, claudepages.dev, claudestudio.com, anthropic.team, antspace.dev and chatbotclaude.com. The earlier marketing/CDN/Auth0/Ghost entries also need evidence before restoration.

The earlier hcaptcha.com, withpersona.com, yoti.com, siftscience.com, intercomassets.com, intercom-messenger.com, r.stripe.com and fcmtoken.googleapis.com entries are not restored without client-specific evidence. Shared telemetry rules do not establish that routing telemetry prevents account restrictions.

No broad google.com, googleapis.com, amazonaws.com, cloudflare.com, auth0.com or stripe.com suffixes are included. ChatGPT Voice IPs are not imported; domain rules alone do not guarantee media connectivity. Enterprise-specific GHE hosts and wildcard Azure report fallbacks require deployment-specific configuration.

The main list includes Chinese and international services under one chosen policy; it does not imply that all require a proxy. A shared dependency may be necessary for authentication even though it is optional to route through the AI policy. Existing general routing can already cover it.

## Community provenance supplied with the research

- [v2fly domain-list-community](https://github.com/v2fly/domain-list-community/tree/master/data)
- [dler-io Rules](https://github.com/dler-io/Rules)
- [SukkaW Surge](https://github.com/SukkaW/Surge)
- [ACL4SSR](https://github.com/ACL4SSR/ACL4SSR)
- [blackmatrix7](https://github.com/blackmatrix7/ios_rule_script)
- [VPSDance](https://github.com/VPSDance/ai-proxy-rules)

These upstream inventories were reported by the supplied research; this review did not independently repeat every upstream or X lookup. Future additions should cite a source and distinguish dedicated hosts from shared hosts.
