+++
title = "Social Icons"
hide_authorbox = true
disable_comments = true
categories = ["Documentation"]
[menu.main]
  weight = 5
  parent = "docs-site"
+++

Social icons are an easy way to link viewers of your site to other parts of your online presence, such as to your Facebook, Twitter, LinkedIn, GitHub, and more. The complete list is below.

<!--more-->

# Setup

Everything here goes under `[Params.social]` in your site's `config.toml` file.

Example (from [Shadow53's blog](https://shadow53.com)):

```
[Params.social]
    linkedin = "shadow53"
    github = "Shadow53"
    steam = "id/shad0w0710"
```

Full list of social links and how to link to them:

- Bitbucket (`bitbucket = "username"`)
- DeviantArt (`deviantart = "username"`)
- Email (`email = "email@domain.com"`)
  - You can also add special parameters after your email address to further customize the new draft that appears for the user. For example:
  `email = "email@example.com?subject=Subject%20Line&
  cc=other@example2.com&body=Default%20body%20text."`
  - Learn more about customizing email links at [CSS Tricks](https://css-tricks.com/snippets/html/mailto-links/).
- Etsy (`etsy = "store-name"`)
- Facebook (`facebook = "userid"`)
    - Your Facebook user id is what comes after "<https://facebook.com/>" on your public profile page
- Flickr (`flickr = "username"`)
- Gitter (`gitter = "user/repo"`)
- GitHub (`github = "username"` or `github = "username/project-name"`)
- GitLab (`gitlab = "username"` or `gitlab = "username/project-name"`)
- Google Plus (`googleplus = "+Joe-Smith"`)
- Instagram (`instagram = "username"`)
- LinkedIn (`linkedin = "userid"`)
- Medium (`medium = "username"`)
- Patreon (`patreon = "username"`)
- Pinterest (`pinterest = "username"`)
    - Your username is whatever follows "<https://pinterest.com/>" on your profile page
- PlayStation (`playstation = "username"`)
- Quora (`quora = "userid"`)
    - Your userid is whatever follows "<https://quora.com/profile/>" on your profile page
- Reddit (`reddit = "username"`)
- Slack Organization (`slack_org = "subdomain"`)
    - Your subdomain is whatever comes after "https://" and before ".slack.com"
- Snapchat (`snapchat = "username"`)
- Soundcloud (`soundcloud = "userid"`)
    - Your userid is whatever comes after "<https://soundcloud.com/>" on your profile page
- Spotify (`spotify = "username"`)
- Steam (`steam = "id/[username]" OR "profiles/[48624573984729386]"`)
  - If you have a custom profile link set up, it will be `id/your-login-username`
  - If not, it will be `profiles/your-steam-userid-number`
  - You may need to look yourself up on the [Steam Community](http://steamcommunity.com/) to figure out which to use. The content you use will be the part of the URL after `steamcommunity.com`
- Telegram (`telegram = "username"`)
- Tumblr (`tumblr = "username"`)
- Twitch (`twitch = "username"`)
- Twitter (`twitter = "username"`)
- Vimeo (`vimeo = "userid"`)
  - It seems some users have custom URLs and some are identified as "user1234567". Use whatever comes after "<https://vimeo.com/>" on your profile page.
- Xbox (`xbox = "username"`)
- YouTube (`youtube = "user/[username]" OR "channel/[channel_name]"`)
  - Use the "user/" option if you have a custom username and your profile URL begins with "<https://youtube.com/user/>". If your profile URL begins with "<https://youtube.com/channel/>" instead, use the "channel/" option.
