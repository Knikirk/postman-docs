---
title: "SCIM provisioning overview"
order: 142
updated: 2022-03-02
page_id: "scim_provisioning_overview"
warning: false
contextual_links:
  - type: section
    name: "Additional Resources"
  - type: subtitle
    name: "Blog Posts"
  - type: link
    name: "Introducing User Management in Postman with SCIM"
    url: "https://blog.postman.com/introducing-user-management-in-postman-with-scim/"
---

> __[Provisioning with SCIM is only available to Postman Enterprise teams.](https://www.postman.com/pricing)__

Postman supports [SCIM](https://datatracker.ietf.org/doc/html/rfc7642) (System for Cross-domain Identity Management), allowing you to automate user provisioning and de-provisioning for your team. With this feature, you can efficiently deploy Postman at scale across your organization and control access to it via your identity provider.

You can enable SCIM provisioning with the [SCIM API](#configuring-scim-with-the-scim-api), [Okta](/docs/administration/scim-provisioning/configuring-scim-with-okta/), or [Azure AD](/docs/administration/scim-provisioning/configuring-scim-with-azure-ad/). You must be a [Postman team admin](/docs/collaborating-in-postman/roles-and-permissions/#team-roles) to enable SCIM for your team. With SCIM enabled, users won't have the option to leave your team on their own, and won't be able to change their account email or password. Only team admins will have the right to remove team members.

## Contents

* [SCIM features](#scim-features)

* [Enabling SCIM provisioning](#enabling-scim-provisioning)

    * [Enabling SCIM in Postman](#enabling-scim-in-postman)

    * [Generating SCIM API key](#generating-scim-api-key)

* [Configuring SCIM with the SCIM API](#configuring-scim-with-the-scim-api)

* [Next steps](#next-steps)

## SCIM features

Postman supports the following provisioning features:

* Create user: Creates a new user account in Postman, adds the account to your organization's Postman team, and activates authentication for the user. If an account with the same email ID exists, an [email invite](/docs/administration/managing-your-team/managing-your-team/#invites) to join your Postman team is sent to the user. Once the user accepts the invite, they will be added to your team.

> The newly added user will have the developer role in Postman by default. You can later [update account roles in Postman](/docs/administration/managing-your-team/managing-your-team/#managing-roles).

* Update user information: Updates a user’s first and last name in Postman.

* Activate user: Creates a new user on your Postman team, if one doesn't already exist, and activates the user to authenticate into your Postman team.

* Deactivate user: Removes a user from your Postman team and deactivates their account, blocking the account from authenticating into Postman.

> The user account and the data corresponding to it won't be deleted. To permanently delete the user account and their data, [contact Postman support](https://www.postman.com/support/).

* Reactivate user: Reactivates an existing deactivated user by unblocking the account's authentication into Postman and adds the account back to your Postman team.

Currently, Postman doesn't support the following provisioning features:

* Push groups
* Import groups
* Push/sync password updates
* Push user attribute updates from Okta to Postman other than name
* Pull user attribute updates from Postman to Okta

## Enabling SCIM provisioning

You must have SSO configured before you can enable SCIM for your Postman team.

> To use SCIM, you must have only one SSO method configured. If you have more than one SSO method enabled, you won't have the option to generate a SCIM API key.

<!-- -->
> Learn [how to configure SSO in Postman](/docs/administration/sso/admin-sso/).

### Enabling SCIM in Postman

To enable SCIM:

1. Navigate to [Postman](https://go.postman.co/home).
1. Select **Team** in the upper right, then select **Team Settings**.
1. Select **Authentication** in the left sidebar.

    <img alt="Enable SCIM in dashboard" src="https://assets.postman.com/postman-docs/auth-enable-scim-v9.jpg"/>

1. Next to **SCIM provisioning**, select the toggle to turn on SCIM provisioning.

    <img alt="Enable SCIM in dashboard" src="https://assets.postman.com/postman-docs/turn-on-scim-provisioning-1.jpg" width="400px"/>

1. Click **Turn On** to enable SCIM provisioning.

### Generating SCIM API key

1. Under **SCIM provisioning**, select **Generate SCIM API Key**.

    <img alt="Generate SCIM API key" src="https://assets.postman.com/postman-docs/generate-scim-api-key-v9.jpg"/>

1. Name your key and click **Generate**.
1. Copy your new API key for later use and click **Done**.

> You can revisit this page to manage your SCIM API keys. If you regenerate an existing API key, you will have the option to keep the first key active briefly while you switch over.

To continue enabling SCIM provisioning, see [Configuring SCIM with the SCIM API](#configuring-scim-with-the-scim-api), [Configuring SCIM with Okta](/docs/administration/scim-provisioning/configuring-scim-with-okta/), or [Configuring SCIM with Azure AD](/docs/administration/scim-provisioning/configuring-scim-with-azure-ad/). For further information or help configuring SCIM, [contact Postman support](https://www.postman.com/support/).

## Configuring SCIM with the SCIM API

Visit Postman's [SCIM API docs](https://www.postman.com/postman/workspace/scim/documentation/6248949-de4a96e2-9ebf-426f-bc55-4c5f2de51ab2) for information on setting up SCIM for your Postman team via the SCIM 2.0 API.

## Next steps

Learn more about [defining roles](/docs/collaborating-in-postman/roles-and-permissions/) in your team and how to [create user groups](/docs/administration/managing-your-team/user-groups/).
