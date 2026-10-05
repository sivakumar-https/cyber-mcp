---
description: Investigate an alert and record a defensible outcome.
icon: compass
---

# Your first investigation

This walkthrough takes an alert through triage, investigation, and closure. Preserve useful evidence in the case record.

{% hint style="info" %}
Use a non-production alert while you learn the workflow.
{% endhint %}

## 1. Assess the alert

Open **Alerts** and review the severity, source, affected asset, and event timeline. Confirm the alert matches the asset context.

Set the priority based on business impact and confidence:

| Priority | Use when                                          |
| -------- | ------------------------------------------------- |
| Critical | Active compromise may affect sensitive systems.   |
| High     | Evidence indicates a likely malicious event.      |
| Medium   | Investigation is required, but impact is limited. |
| Low      | Review during routine triage.                     |

## 2. Create a case

{% stepper %}
{% step %}
#### Assign an owner

Assign the alert to an analyst. Add a due time for high-priority work.
{% endstep %}

{% step %}
#### Collect evidence

Review related alerts, identity activity, and asset history. Add the relevant evidence to the case timeline.
{% endstep %}

{% step %}
#### Record the outcome

Choose **Resolved** only after recording the decision:

* **Benign** — expected activity triggered the alert.
* **False positive** — detection logic needs adjustment.
* **Confirmed incident** — containment or escalation is required.
{% endstep %}
{% endstepper %}

## 3. Customise your build

The platform auto-detects most frameworks, but you can override the defaults in your project's `platform.yaml`:

```yaml
build:
  command: npm run build
  output: dist/
  node: 20
  install: npm ci

deploy:
  framework: auto
  routes:
    - source: /api/*
      destination: /api/[...path].js
```

Common overrides:

* **`build.command`** — the script that produces your output
* **`build.output`** — the folder containing your built files
* **`build.node`** — the Node.js version to use
* **`deploy.routes`** — custom routing rules

## 4. Set up preview deploys

Preview deploys give every branch and pull request its own live URL. They're enabled by default, but you can fine-tune the behaviour:

```yaml
preview:
  enabled: true
  branches:
    include: ["**"]
    exclude: ["release/*"]
  comments: true
```

When `comments: true`, the platform posts a comment on each pull request with the preview URL.

## 5. Deploy

Push to your main branch (or click **Deploy** manually). The platform will:

1. Clone your repository
2. Install dependencies
3. Run your build command
4. Upload the output
5. Promote to your live URL

{% hint style="success" %}
You'll get a notification when the build completes — by email, Slack, or whatever you configured under [automations.md](../guides/automations.md "mention").
{% endhint %}

## Sample project

If you'd like to skip ahead and see a fully configured project, download our sample:

{% embed url="https://github.com/GitbookIO/gitbook-templates" %}

## Where to go next

Now that you have a working project, you can check out:

{% content-ref url="../guides/custom-domains.md" %}
[custom-domains.md](../guides/custom-domains.md)
{% endcontent-ref %}

{% content-ref url="../guides/automations.md" %}
[automations.md](../guides/automations.md)
{% endcontent-ref %}

{% content-ref url="../core-concepts/permissions.md" %}
[permissions.md](../core-concepts/permissions.md)
{% endcontent-ref %}
