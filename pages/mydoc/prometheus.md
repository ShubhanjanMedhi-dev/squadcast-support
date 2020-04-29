---
title: Prometheus
tags: [integration, prometheus]
keywords: 
last_updated: 
summary: "Send events to Squadcast from Prometheus"
sidebar: mydoc_sidebar
permalink: prometheus.html
folder: mydoc
---

Follow the steps below to configure a service so as to extract its related alert data from Prometheus.

Squadcast will then process this information to create incidents for this service as per your preferences.

## Using Prometheus as an Alert Source

On the **Sidebar**, click on **Services**.

You can either choose to use existing service or [create a new service](adding-a-service.html)

Now, click on the corresponding **Alert Sources** button.

![](images/integration_1.png)

Select **Prometheus** from **Alert Source** drop down and copy the Webhook URL shown.

![](images/prometheus_1.png)

## Create a Squadcast Webhook in Prometheus

Now open your Prometheus Alertmanager's Configuration file. (You need Prometheus Alertmanager to handle alerts generated by Prometheus. [Click here for more information ](https://prometheus.io/docs/alerting/alertmanager/))

Add a new webhook receiver and enter the URL obtained earlier as the webhook url.

![](images/prometheus_2.png)

Now you can use this receiver in any of your alert routes (You can also make it the default receiver, as per your requirements).

![](images/prometheus_3.png)

Also please make sure that your alerts has the severity under labels, and annotations has the summary & description fields configured in the alert rules file as shown below in the example rules config.

```yaml
serverFiles:
  alerts:
    groups:
    - name: gt.k8s.kafka.rules
      rules:
      - alert: GtK8sKafkaConsumerLag1Warning
        expr: kafka_consumergroup_lag > 500
        for: 120m
        labels:
          severity: warning
        annotations:
          description: "Kafka consumer { { $labels.consumergroup } } lags with { { $value } } messages in topic { { $labels.topic } }"
          summary: "Kafka affected in { { $labels.instance } }"
```

**Important**: We use the summary field along with Severity & Alert group name as incident message and the description field along with generator url as incident description. Hence, **severity (labels), summary & description (annotations)** are mandatory for integration with Squadcast.

**Note**: Any alert which gets resolved from Prometheus will automatically be resolved inside Squadcast as well, unless you have explicitly set **send_resolved** to false in the config file.

<style>.btttn:hover{box-shadow: 0 10px 20px 0 rgba(15,97,221,.25); transform: translate(0,-2px);}</style><div style="height: 100%;width: 100%;display: flex;margin-top: 40px;"><div style="margin: auto;"><div style="height: 100%;width: 100%;display: flex;padding: 20px;border: 1px solid #e7e9ed;border-radius: 8px;"><div style="margin: auto;"><div style="text-align: center;padding-bottom: 20px;font-size: 18px;line-height: 24px;font-family: Metropolis, sans-serif;color: #0d2149;">Ready to try Squadcast?</div><a href="https://app.squadcast.com/register" class="btttn" target="_blank" style="margin-right: 0;text-decoration: none;border-radius: 6px;background-color: #0f61dd;font-family: Metropolis,sans-serif;color: #fff;padding-top: 0;padding-bottom: 0;border-bottom: 1px solid transparent;-webkit-transition: all .1s ease-in-out;font-family: Metropolis,sans-serif;font-size: 13px;color: #0d2149;line-height: 22px;font-weight: 500;display: inline-block;color: #fff;padding: 15px;text-align: left;margin-left: auto;margin-right: auto;max-width: 1200px;transition: all .2s ease-in-out;" rel="noreferrer noopener">Start Now For Free!</a>   <a href="https://calendly.com/amiya-squadcast/website?month=2019-08&amp;back=1" class="btttn" target="_blank" style="margin-right: 0;text-decoration: none;border-radius: 6px;background-color: #fff;font-family: Metropolis,sans-serif;color: #0f61dd;padding-top: 0;padding-bottom: 0;border-bottom: 1px solid transparent;-webkit-transition: all .1s ease-in-out;font-family: Metropolis,sans-serif;font-size: 13px;color: #0d2149;line-height: 22px;font-weight: 500;display: inline-block;color: #0f61dd;padding: 15px;text-align: left;margin-left: auto;margin-right: auto;max-width: 1200px;border: 1px solid #0f61dd;margin-left: 20px;transition: all .2s ease-in-out;" rel="noreferrer noopener">Schedule a Demo</a></div></div></div></div>