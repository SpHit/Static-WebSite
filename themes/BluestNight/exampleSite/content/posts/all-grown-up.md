+++
title = "BluestNight is All Grown Up!"
date = "2017-09-10T10:26:15-07:00"
hide_authorbox = false
disable_comments = false
categories = ["Announcements"]
tags = ["releases", "bug fixes", "features"]
aliases = ["/post/all-grown-up/"]
+++

On March 20th, 2017, I made the first commit in the BluestNight repository. Back then, BluestNight was little more than my attempt to create a cleaner-written version of the [Mainroad](https://themes.gohugo.io/mainroad) theme after I grew frustrated with maintaining the fork I made, named "Darkroad" (it was a dark version of Mainroad).

<!--more-->

The first iteration of BluestNight was built using the [Foundation](https://foundation.zurb.com) CSS framework by Zurb. It worked well for quickly building the skeleton of the theme, but I've never been one for using frameworks when I don't actually need them. So, after learning about the existence of the flex box CSS model, I decided to scrap Foundation in favor of a [few custom classes](https://gitlab.com/BluestNight/BluestNight/blob/master/layouts/partials/css/screen_size.css) using flex.

I had also implemented custom color support from the beginning, using a static CSS file combined with inlined CSS overrides at the top of every page. This worked well enough, except for when the override didn't actually override the base setting (because the base rule was more specific than the override). That changed when Hugo 0.20.0 was released on April 10th with [custom output format](https://gohugo.io/templates/output-formats/) support - now I could generate the CSS with custom colors from the beginning, no overrides needed!

All of the features in BluestNight are either (a) features I use or (b) alternatives to the features I use for people wanting something different. The nice thing about this is that most features available in BluestNight get used on a site that I maintain, which helps greatly with catching bugs before changes get published. Being a user of the features myself, I also have a better idea of what a user would want from this theme, and I think it shows.

Anyhow, BluestNight has graduated from being "just" a personal project. It's still developed almost solely by me, but it's become more than "that theme I made" - enough so that I decided to make a BluestNight group [on GitLab](https://gitlab.com/BluestNight) (equivalent to a GitHub organization). This decision was also in part due to my plans to create a utility to help people maintain their Hugo websites, including support for various themes (more on that in a future update).

BluestNight is still the same great theme you love - or maybe you've yet to love it. In that case, take some time to look around, [check out the documentation]({{< static "/docs/" >}}), see what you think. If you like it, why not support development of this theme on [Patreon](https://patreon.com/shadow53)? Building a theme like this is a lot of work, which is hard when you spend your time instead doing work that pays you. Even a dollar or two per month helps.

If you're interested in staying up to date with BluestNight development, why don't you subscribe to updates using your favorite RSS reader? Just click the "Subscribe" button in the sidebar.
