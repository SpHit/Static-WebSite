+++
title = "Comments"
hide_authorbox = true
disable_comments = true
categories = ["Documentation"]
enable_toc = true
[menu.main]
  weight = 2
  parent = "docs-pages"
+++

BluestNight currently supports two comment providers:

- [HashOver](comments/hashover), a self-hosted provider using PHP
- [Muut](comments/muut), a third-party service using only JavaScript

This page details options that apply regardless of which service you are using.

<!--more-->

# Enable/disable comments site-wide

If you have enabled a certain comment provider in your site configuration file, that comment provider is enabled across the whole site (though it can be disabled on a per-page basis). To disable comments across the whole site, just remove or comment out the option in the configuration file.

# Disable comments on a specific page

To disable comments on a specific page, set `disable_comments` to `true` in the page's [front matter](http://gohugo.io/content/front-matter/).

```
+++
title = "My Comment-Free Page"
disable_comments = true
+++

Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nullam consectetur tempus tortor, eget bibendum ipsum ultricies sed. Suspendisse arcu enim, porta non sollicitudin quis, gravida ornare nulla. In vel diam felis. Nam neque mauris, facilisis non nibh in, elementum porta libero. Sed dolor arcu, tincidunt non augue porta, euismod lacinia nibh. Sed faucibus risus massa, eget fermentum tortor efficitur a. Donec sed mi sagittis, consectetur nibh eget, mollis dolor. Nulla feugiat sodales dolor non gravida. Integer semper tempor massa id tincidunt.
```

# Hashover

BluestNight supports using the [HashOver](http://tildehash.com/?page=hashover) self-hosted comment system. Note that this comment system **requires PHP** and cannot be used on services that do not support PHP.

## Notes
- This guide assumes that you have a server set up to use PHP.**
- All relative paths are relative to the root of your Hugo site
  - This means that BluestNight is installed to `themes/BluestNight`

## Installation

BluestNight has HashOver bundled with it, so you do not need to do anything to "install" it as of this time. This may change in the future.

## Setup

- Set `Params.hashover` to `true` in your site's configuration file
- Copy the file `secrets.php` from `themes/BluestNight/static/hashover/scripts/secrets.php` to `static/hashover/scripts/secrets.php`. This prevents your changes from be overridden on updates to the theme.
- Open `static/hashover/scripts/secrets.php` in your favorite text editor and find these lines:

```php
$encryption_key     = '8CharKey';                // Unique 8 to 32 character encryption key
$notification_email = 'example@example.com';     // E-mail for notification of new comments
$admin_nickname     = 'admin';                   // Nickname with admin rights (must be title-cased)
$admin_password     = 'passwd';                  // Password to gain admin rights
```

- Replace the encryption key with a randomly generated key, such as from [this generator](http://passwordsgenerator.net/).
- Replace the notification email with one that you want to receive notifications of new comments.
- Replace the admin password with a *secure* password that you can use to verify yourself to delete/edit comments and perform other administrative actions.

## Customization

Custom color schemes are applied to HashOver comments.

# Muut

For those who don't want to also host the comments on their site, BluestNight provides support for [Muut](https://muut.com/). For more about the decision to support Muut, [click here](https://shadow53.com/post/new-social-features/#comments-by-muut).

[Click here](https://muut.com/pricing/) for a current comparison between the free and paid tiers of Muut's service.

## Setup

To begin, [sign up for a free Muut account](https://muut.com/setup/). Make sure to keep track of the name you give your Muut Community, as you will need that information later. You may be automatically enrolled in a free trial of a paid subscription. You will be dropped down to a free subscription at the end of the trial.

Remember the name you gave your Muut community? That will go in your site's configuration file as the value for `muut` under `Params`:

```
# In config.toml

[Params]
    muut = "mycommunity"
```

After running `hugo`, you should now have Muut comments on all pages you [have them enabled on](comments).
