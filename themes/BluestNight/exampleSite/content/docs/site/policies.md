+++
title = "Website Policies"
linktitle = "Policies"
hide_authorbox = true
disable_comments = true
enable_toc = true
description = ""
categories = ["Documentation"]
[menu.main]
  weight = 3
  parent = "docs-site"
+++

BluestNight currently supports two methods of including privacy policies (and other website policy documents) as links in the footer of the site.

## Custom Files

The first is to create the documents `privacy-policy.md` and/or `terms-of-use.md` in the root of the content directory (i.e. `content/privacy-policy.md`). They will be detected and have links in the footer under the copyright.

## Iubenda Integration

The second is an integration with [Iubenda](http://iubenda.refr.cc/FMFBN89), a service that allows users to select how they collect user information - comment systems, analytics, forms, etc. - and generates a privacy policy that can be viewed at the click of a button. A free account with Iubenda does not allow for modification of this button, however, aside from whether it is white or black.

### Base Iubenda configuration

To use the Iubenda integration, set `id` and optionally `color` and `legal_only` under `Params.iubenda` in the site's configuration file. For example:

```
[Params.iubenda]
  id = "1234567"
  # "black" and "white" are the only valid options
  # Leave unset to automatically match the footer background
  # as much as possible
  color = "black"
  # Set to true to not display the user-friendly version of the policy
  legal_only = true
```

To get the `id`, [log in to Iubenda](https://www.iubenda.com/en/login) and go to the "Integration" tab for the policy you want to include. In the embedding code under "Integrate the policy", there will be a bit of code looking something like `<a href="//www.iubenda.com/privacy-policy/1234567"` - the numbers after "//www.iubenda.com/privacy-policy/" are the `id`.

### Configuration for Iubenda Pro Accounts

{{% alert %}}
These options are only for Iubenda Pro users and **will not work with a free account!** The `enable_pro` parameter **must** be set to `true` to be able to use any of these Pro features. Pro features also require the above `id` parameter to be set.
{{% /alert %}}



```
[Params.iubenda.pro]
  # Required to use pro features
  enable_pro = true
  # Set to true to enable the cookie banner
  enable_cookie_policy = true
  # Site ID for the cookie banner
  site_id = "908104"
  # Disable the footer button if using the shortcode
  disable_footer_link = true
  # Set to false to load tracking scripts before getting user consent
  prior_consent = true
```

#### Cookie Banner

Iubenda Pro accounts have access to a feature that displays a cookie consent banner when someone first visits the site. To enable this feature, set `enable_cookie_policy` to `true` and `site_id` to the site ID displayed in the consent banner embed code.

{{< figure src="/images/docs/site/policies/consent_banner_embed.png" title="Consent Banner Embed Code" caption="The 'siteId' parameter corresponds with BluestNight's 'site_id', while 'cookiePolicyId' corrsponds with BluestNight's 'id' parameter." >}}

Iubenda Pro offers the ability to prevent tracking scripts from loading until the user accepts the cookie policy, free up to 25,000 monthly page views. It also, however, offers a "light" cookie solution that does *not* prevent tracking scripts from loading and is always free. Note that Iubenda warns that prior consent - blocking tracking until the user consents - is required by "most EU legislations" and thus the "full" solution is recommended.

To choose between the two solutions, change the `prior_consent` parameter. A value of `true` enables the "full" solution and `false` enables the "light" version.

#### Iubenda Shortcode

Pro accounts also have the ability to access the privacy policy over a JSON api endpoint. What this means for BluestNight users is that Hugo can download the contents of the privacy policy once while building the site, rather than loading the text using JavaScript every time the page is loaded.

The recommended way to do this is to create the `privacy-policy.md` file in the root of your content directory and use the shortcode in place of any page content. If your site's configuration file is set up correctly, the following should be enough to create your privacy policy page.

```
+++
title = "Privacy Policy"
+++

{{</* iubenda */>}}
```
