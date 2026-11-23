# China rules import review — 2026-11-23

## Result

Imported the user-supplied china.list after reviewing its accompanying changes, evidence, coverage, unverified-candidate and search-log documents. All 39 existing rules are retained verbatim. The update adds 17 domain rules (56 total), with no IP, ASN, process, keyword or User-Agent rules. Existing ai.list and outbank.list are unchanged.

## Added rules

```text
DOMAIN,dldir1v6.qq.com
DOMAIN-SUFFIX,alipay.cn
DOMAIN-SUFFIX,alipay.com.cn
DOMAIN-SUFFIX,alipay.hk
DOMAIN-SUFFIX,alipaydns.com
DOMAIN-SUFFIX,alipaymo.com
DOMAIN-SUFFIX,alipayplus.com
DOMAIN-SUFFIX,cainiao.com
DOMAIN-SUFFIX,cainiao.com.cn
DOMAIN-SUFFIX,taobaocdn.com
DOMAIN-SUFFIX,tbcache.com
DOMAIN-SUFFIX,tbcdn.cn
DOMAIN-SUFFIX,wechatpay.cn
DOMAIN-SUFFIX,weixin.qq.com.cn
DOMAIN-SUFFIX,wx2.qq.com
DOMAIN-SUFFIX,wx8.qq.com
DOMAIN-SUFFIX,wxqcloud.qq.com.cn
```

## Evidence boundary

Most provenance is from the supplied research and was not independently repeated. Its comments preserve the distinction between official references, community observations and unverified baseline entries. Search-log claims and source timestamps are not certified by this import.

The [WeChat Web page](https://wx2.qq.com/) was independently opened and identified as WeChat/Weixin for Web. The WeChat Pay certificate-notice page could not be retrieved by the web tool, and the Alipay+ homepage timed out; neither was treated as a successful independent verification. These failures do not establish that the domains are invalid.

Reported source groups:

- WeChat web/download/developer resources: [WeChat](https://weixin.qq.com/), [wx2](https://wx2.qq.com/), [wx8](https://wx8.qq.com/), [mini-program networking](https://developers.weixin.qq.com/miniprogram/dev/framework/ability/network.html).
- WeChat Pay: [certificate notice](https://pay.weixin.qq.com/index.php/public/wechatpay_en/server_cert_notif/), [official Java SDK](https://github.com/wechatpay-apiv3/wechatpay-java), [face-payment terminal network guidance](https://pay.wechatpay.cn/wiki/doc/wxfacepay/faq/network.html). Terminal IP allowlists are not adopted as personal-app destinations.
- Community Alipay/CDN entries: [v2fly Alibaba data](https://github.com/v2fly/domain-list-community/blob/master/data/alibaba), [blackmatrix7 AliPay](https://github.com/blackmatrix7/ios_rule_script/blob/master/rule/Surge/AliPay/AliPay.list). Some official portal pages were unreadable in the supplied research; these entries remain community-supported.
- Cainiao: [official website](https://www.cainiao.com/), [community data](https://github.com/v2fly/domain-list-community/blob/master/data/cainiao). Platform attribution and delivery-data sharing do not prove an app always contacts these domains.

## Coverage and unresolved candidates

The list adds web-login siblings, WeChat developer resources, the Pay .cn domain, Alipay DNS/regional products, legacy Taobao CDNs and Cainiao. Shared resources can match other products. Regional Alipay domains are included under the same chosen policy, even when they are not needed by mainland-app sessions.

No real-client login, payment, upload or voice/video call was tested. IP-only connections, peer-to-peer media and arbitrary merchant/mini-program backends remain gaps. Existing GEOIP or other rules may handle some traffic outside this list, but that is not a completeness guarantee.

The supplied report leaves short-link/streaming/cloud candidates (mmbizurl.cn, wxaurl.cn, wxmpurl.cn, wxlivecdn.com, wxgateway.com and wxcloudrun.com), additional Alipay development/internal domains and ambiguous Xianyu domains inactive pending evidence. It also leaves specific shared captcha/support/push hosts for future review; being shared alone is not evidence that a host is unnecessary.

No broad qq.com, gtimg.com, aliyuncs.com, cloud ASN or old device-specific IP inventory is newly imported. Existing uncertain baseline entries, including slife.xy-asia.com, remain explicitly preserved. New research must not silently delete or narrow the user's maintained baseline.

## Validation

All 39 original rule strings are present; all 17 additions are accounted for. Syntax, duplicates and suffix-covered redundancy were checked. This validates rule structure and preservation, not live application connectivity.
