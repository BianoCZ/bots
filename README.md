# BIANO Bots

This page documents the automated bots operated by **Biano** ([biano.com](https://www.biano.com)).
All bots are transparent about their identity and purpose, and comply with `robots.txt`.

For questions or to report issues, contact: [it@biano.com](mailto:it@biano.com)

---

## Bots

### Feed Fetcher

Downloads XML product feeds from registered eshops.

| Field          | Value                                                                                                                                                               |
|----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **User-Agent** | `BianoBot-FeedFetcher/1.0 (+https://github.com/BianoCZ/bots#feed-fetcher)`                                                                                          |
| **Purpose**    | Fetches XML product feed files over HTTP GET for product catalogue synchronization, using a content hash to skip unchanged feeds. Does not store any personal data. |
| **Access**     | Direct — operated by Biano                                                                                                                                          |
| **IP Ranges**  | [ips.json](https://raw.githubusercontent.com/BianoCZ/bots/main/ips.json)                                                                                            |

---

### Image Fetcher

Downloads product images from registered eshops.

| Field          | Value                                                                                                                                                        |
|----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **User-Agent** | `BianoBot-ImageFetcher/1.0 (+https://github.com/BianoCZ/bots#image-fetcher)`                                                                                 |
| **Purpose**    | Downloads product images (in parallel, throttled per domain and honoring HTTP 429 rate limits) for display on marketplace. Does not store any personal data. |
| **Access**     | Direct — operated by Biano                                                                                                                                   |
| **IP Ranges**  | [ips.json](https://raw.githubusercontent.com/BianoCZ/bots/main/ips.json)                                                                                     |

---

### Redirect Resolver

Resolves the final destination of promotional, affiliate, and review-source links.

| Field          | Value                                                                                                                                                                                                 |
|----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **User-Agent** | `BianoBot-RedirectResolver/1.0 (+https://github.com/BianoCZ/bots#redirect-resolver)`                                                                                                                  |
| **Purpose**    | Sends HTTP HEAD requests to follow redirect chains and determine a link's final URL, before using that URL elsewhere (e.g. showing a promotion, or fetching reviews). Does not download page content. |
| **Access**     | Direct — operated by Biano                                                                                                                                                                            |
| **IP Ranges**  | [ips.json](https://raw.githubusercontent.com/BianoCZ/bots/main/ips.json)                                                                                                                              |

---

### Eshop Checker

Monitors registered eshop URLs to detect availability issues.

| Field          | Value                                                                                                                                                                                                  |
|----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **User-Agent** | `BianoBot-EshopChecker/1.0 (+https://github.com/BianoCZ/bots#eshop-checker)`                                                                                                                           |
| **Purpose**    | Sends HTTP GET requests to an eshop's homepage plus a small random sample of its product URLs to verify they return HTTP 200. Flags the eshop only if most requests fail. Does not store page content. |
| **Access**     | Direct — operated by Biano                                                                                                                                                                             |
| **IP Ranges**  | [ips.json](https://raw.githubusercontent.com/BianoCZ/bots/main/ips.json)                                                                                                                               |

---

### Platform Detector

Identifies which e-commerce platform a registered eshop runs on.

| Field          | Value                                                                                                                                              |
|----------------|----------------------------------------------------------------------------------------------------------------------------------------------------|
| **User-Agent** | `BianoBot-PlatformDetector/1.0 (+https://github.com/BianoCZ/bots#platform-detector)`                                                               |
| **Purpose**    | Sends a single HTTP GET to an eshop's homepage and scans the returned HTML for markers of known e-commerce platforms. Does not store page content. |
| **Access**     | Direct — operated by Biano                                                                                                                         |
| **IP Ranges**  | [ips.json](https://raw.githubusercontent.com/BianoCZ/bots/main/ips.json)                                                                           |

---

### GTM Checker

Verifies that Biano's tracking tag is correctly injected on a registered eshop's site.

| Field          | Value                                                                                                                                              |
|----------------|--------------------------------------------------------------------------------------------------------------------------------------------------|
| **User-Agent** | `BianoBot-GtmChecker/1.0 (+https://github.com/BianoCZ/bots#gtm-checker)`                                                                          |
| **Purpose**    | Drives a headless browser to an eshop's site to confirm the shared Biano GTM container fires correctly inside the eshop's own tag manager setup. |
| **Access**     | Direct — operated by Biano                                                                                                                        |
| **IP Ranges**  | [ips.json](https://raw.githubusercontent.com/BianoCZ/bots/main/ips.json)                                                                          |

---

### Newsletter Subscriber

Signs up to a registered eshop's own newsletter on Biano's behalf.

| Field          | Value                                                                                                                                           |
|----------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
| **User-Agent** | `BianoBot-NewsletterSubscriber/1.0 (+https://github.com/BianoCZ/bots#newsletter-subscriber)`                                                    |
| **Purpose**    | Uses a headless browser to locate and complete an eshop's newsletter opt-in form, falling back to its account registration form if none exists. |
| **Access**     | Direct — operated by Biano                                                                                                                      |
| **IP Ranges**  | [ips.json](https://raw.githubusercontent.com/BianoCZ/bots/main/ips.json)                                                                        |

---

## Robots.txt Compliance

All bots respect `robots.txt` directives. To block any of our bots, add the following to your `robots.txt`:

```
User-agent: BianoBot-EshopChecker
User-agent: BianoBot-FeedFetcher
User-agent: BianoBot-ImageFetcher
User-agent: BianoBot-RedirectResolver
User-agent: BianoBot-NewsletterSubscriber
User-agent: BianoBot-GtmChecker
Disallow: /
```

---

## Contact

If you have any questions or concerns about our bots, please contact us at [it@biano.com](mailto:it@biano.com).