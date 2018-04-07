+++
title = "Events"
hide_authorbox = true
disable_comments = true
categories = ["Documentation"]
alert = "The events system in BluestNight previously used data files, but now uses content files instead. Be sure to update your site accordingly. More info [here](https://bluestnight.shadow53.com/posts/events-overhauled/)."
[menu.main]
  weight = 2
  parent = "docs-sidebar"
+++

You have a list of events you want to share with your reader base - why not display them on your site?

BluestNight provides both a sidebar widget to display the 5 earliest occurring events listed and a template for a `.ics` calendar file that readers can subscribe to.

<!--more-->

# Setup

Create a new content file in the `events` section of your site. The easiest way to do this is to use the `hugo new` command:

```
hugo new events/some-event.md
```

Hugo should automatically populate the front matter of the file with the appropriate variables:

- `title`: The title of the event (and its related page).
- `location`: The location of the event.
- `start_date`: The starting datetime of the event.
- `end_date`: The ending datetime of the event.
- `doors_open`: The datetime representing when the doors open (where `start_date` represents when people can start lining up for the doors).

To enable events on your site, set `upcoming_events` to `true` under `Params.widgets` in your sites configuration folder:

```
# In config.toml

[Params.widgets]
    upcoming_events = true
```

# Limitations

- Items do not automatically disappear from the sidebar
  - BluestNight automatically filters out events that have already passed when adding events to the sidebar, but it cannot dynamically remove them as they pass, due to it being a static site. It is on the site administrator to at least rebuild the site after an event has passed, though I suggest considering removing the data file as well.
