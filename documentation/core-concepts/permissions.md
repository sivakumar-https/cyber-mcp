---
description: Roles and access controls for your security workspace.
icon: lock
---

# Permissions

Every workspace member has a role. Roles control access to sources, investigations, and administration.

## Roles overview

Use these roles to separate investigation from administration:

| Role          | Best for                                        |
| ------------- | ----------------------------------------------- |
| **Viewer**    | Stakeholders who need read-only visibility      |
| **Analyst**   | Team members who triage alerts and manage cases |
| **Responder** | Analysts authorized to run response actions     |
| **Admin**     | Workspace owners and security administrators    |

{% hint style="info" %}
Grant the least privilege needed. Review responder access regularly.
{% endhint %}

## Permission matrix

The full breakdown of what each role can do:

| Action                       | Guest | Viewer | Reviewer | Editor | Admin |
| ---------------------------- | :---: | :----: | :------: | :----: | :---: |
| View published deploys       |   ✓   |    ✓   |     ✓    |    ✓   |   ✓   |
| View drafts                  |   —   |    ✓   |     ✓    |    ✓   |   ✓   |
| Comment on deploys           |   —   |    —   |     ✓    |    ✓   |   ✓   |
| Trigger builds               |   —   |    —   |     —    |    ✓   |   ✓   |
| Edit project settings        |   —   |    —   |     —    |    ✓   |   ✓   |
| Manage environment variables |   —   |    —   |     —    |    ✓   |   ✓   |
| Invite members               |   —   |    —   |     —    |    —   |   ✓   |
| Change roles                 |   —   |    —   |     —    |    —   |   ✓   |
| Manage billing               |   —   |    —   |     —    |    —   |   ✓   |
| Delete projects              |   —   |    —   |     —    |    —   |   ✓   |

## How permissions flow

Roles are assigned at the **workspace level** and apply to every project in that workspace. There's no per-project override.

If you need finer-grained access — for example, contractors who should only see one project — create a separate workspace for that work and invite them there.

{% hint style="warning" %}
Per-project roles are a frequently requested feature and are on our [roadmap](https://example.com/roadmap). For now, the workspace boundary is the boundary of access.
{% endhint %}

## Changing someone's role

Workspace admins can change any member's role at any time:

1. Go to **Workspace settings → Members**
2. Find the member and click the role dropdown next to their name
3. Select the new role and confirm

The change takes effect immediately — the member doesn't need to re-authenticate.

## Removing a member

Removing a member revokes their access immediately. Any content they created stays in the workspace.

{% hint style="danger" %}
If you're using SSO, removing a member from your identity provider does **not** automatically remove them from the workspace unless SCIM provisioning is enabled.
{% endhint %}
