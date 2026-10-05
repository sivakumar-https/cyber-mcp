---
description: Connect a source and triage your first alert.
icon: bolt
---

# Quickstart

This quickstart connects one source and establishes a basic triage workflow.

{% hint style="success" %}
**Estimated time: 10 minutes.** You need an account and source administrator access.
{% endhint %}

## Steps

{% stepper %}
{% step %}
#### Create your workspace

Sign in and create a workspace for one security team or business unit. Use a clear name.

`Northstar Security`
{% endstep %}

{% step %}
#### Connect a source

Open **Settings → Data sources** and select your source. Grant the minimum read permissions required.

{% tabs %}
{% tab title="Endpoint security" %}
Connect your endpoint provider. Cyber MD begins ingesting alerts after authorization.
{% endtab %}

{% tab title="Cloud" %}
Connect a cloud account with a read-only role. Select the subscriptions or projects to monitor.
{% endtab %}

{% tab title="Identity" %}
Connect your identity provider to ingest sign-in, directory, and risk events.
{% endtab %}
{% endtabs %}
{% endstep %}

{% step %}
#### Set alert routing

Assign an owner for new alerts. Choose a queue that your team monitors.

Start with `Security Operations` as the default queue.
{% endstep %}

{% step %}
#### Triage an alert

Open **Alerts** and select a new alert. Review the affected asset, evidence, and related activity. Set a status, owner, and priority.

{% hint style="info" %}
Do not close an alert until you record the reason and any containment action.
{% endhint %}
{% endstep %}
{% endstepper %}

## What's next?

{% content-ref url="your-first-investigation.md" %}
[your-first-investigation.md](your-first-investigation.md)
{% endcontent-ref %}

{% content-ref url="../core-concepts/permissions.md" %}
[permissions.md](../core-concepts/permissions.md)
{% endcontent-ref %}

{% content-ref url="../guides/automations.md" %}
[automations.md](../guides/automations.md)
{% endcontent-ref %}
