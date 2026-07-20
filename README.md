# BIANO Bots

This page documents the automated bots operated by **Biano** ([biano.com](https://www.biano.com)).
All bots are transparent about their identity and purpose, and comply with `robots.txt`.

For questions or to report issues, contact: [it@biano.com](mailto:it@biano.com)

---

## Bots

### Eshop Checker


Monitors registered eshop URLs to detect availability issues.

| Field | Value                                                                                              |
|---|----------------------------------------------------------------------------------------------------|
| **User-Agent** | `Biano-EshopChecker/1.0 (+https://github.com/BianoCZ/bots#eshop-checker)`                            |
| **Purpose** | Sends HTTP GET requests to an eshop's homepage plus a small random sample of its product URLs to verify they return HTTP 200. Flags the eshop only if most requests fail. Does not store page content. |
| **Access** | Direct — operated by Biano                                                           |
| **IP Ranges** | [ips.json](https://raw.githubusercontent.com/BianoCZ/bots/main/ips.json)                             |

---

### Feed Fetcher

Downloads XML product feeds from registered eshops.

| Field | Value |
|---|---|
| **User-Agent** | `Biano-FeedFetcher/1.0 (+https://github.com/BianoCZ/bots#feed-fetcher)` |
| **Purpose** | Fetches XML product feed files over HTTP GET for product catalogue synchronization, using a content hash to skip unchanged feeds. Does not store any personal data. |
| **Access** | Direct — operated by Biano |
| **IP Ranges** | [ips.json](https://raw.githubusercontent.com/BianoCZ/bots/main/ips.json) |

---

### Image Fetcher

Downloads product images from registered eshops.

| Field | Value                                                                                                                                                            |
|---|------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **User-Agent** | `Biano-ImageFetcher/1.0 (+https://github.com/BianoCZ/bots#image-fetcher)`                                                                                        |
| **Purpose** | Downloads product images (in parallel, throttled per domain and honoring HTTP 429 rate limits) for display on marketplace. Does not store any personal data. |
| **Access** | Direct — operated by Biano                                                                                                                                       |
| **IP Ranges** | [ips.json](https://raw.githubusercontent.com/BianoCZ/bots/main/ips.json)                                                                                         |

---

## Robots.txt Compliance

All bots respect `robots.txt` directives. To block any of our bots, add the following to your `robots.txt`:

```
User-agent: Biano-EshopChecker
User-agent: Biano-FeedFetcher
User-agent: Biano-ImageFetcher
Disallow: /
```

---

## Contact

If you have any questions or concerns about our bots, please contact us at [it@biano.com](mailto:it@biano.com).