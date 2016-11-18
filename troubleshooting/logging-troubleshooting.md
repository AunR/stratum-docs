---
title: Logging Troubleshooting
category: troubleshooting
---

# Logging Troubleshooting

## Logging is down

**I am getting a 503 when I try to view my logging page pod0XXX.catalyzeapps.com/logging**

- **Potential Issue:** Your logging service may be down or may not have been deployed
- **Potential Solution:** For some sandbox environments, logging services may not have been created. Contact [Catalyze support](https://resources.catalyze.io/stratum/articles/contact/) to create and deploy these services.  Otherwise you can trigger a [redeploy](https://resources.catalyze.io/paas/paas-cli-reference/redeploy/#redeploy) of your logging service by using the Catalyze CLI command `catalyze redeploy logging`.

**CircuitBreakerException: Data too large**

- **Potential Issue:** This usually occurs when your logging service has accumulated a large amount of data and [Elasticsearch](https://www.elastic.co/products/elasticsearch) is reaching its memory usage cap.
- **Potential Solution:**  Contact [Catalyze support](https://resources.catalyze.io/stratum/articles/contact/) to increase Elasticsearch's memory usage limit or clear Elasticsearch's cache.

## Missing Logs

**I am not seeing any logs for a service in my logging dashboard**

- **Potential Issue:** Logs may not be printing properly to `stdout`. If you are using custom logging, your application may not be configured properly.
- **Potential Solution:** Ensure you are printing log messages to `stdout`.  If you want to use custom logging, ensure it has been set up and configured properly according to [this guide](https://resources.catalyze.io/stratum/articles/guides/application-logging/).