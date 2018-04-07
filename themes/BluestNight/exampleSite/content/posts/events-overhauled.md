+++
title = "Events: Overhauled"
date = "2017-10-17T10:26:15-07:00"
hide_authorbox = false
disable_comments = false
categories = ["Announcements"]
tags = ["releases", "bug fixes", "features", "events"]
+++

Time for another big update to BluestNight! In this episode, the events system has been overhauled to look nicer and provide more functionality than previously. Also, a some other semantic changes to watch out for while updating.
<!--more-->
# Events

Events have been changed from data to content files, to better give visitors information about any events held by the owner of the site. Visitors can now visit pages for previous events and see what is coming past the five most immediate events.

## Before

The previous method of doing events involved [data files](https://gohugo.io/templates/data-templates/) with information relating to the events. Those data files were then parsed and assembled into an [iCalendar](https://en.wikipedia.org/wiki/ICalendar) file; the five most immediate upcoming events were also put into the sidebar of the website for easy viewing.

## After

The iCalendar file and sidebar reminders are still there, but the sidebar widget has been reformatted slightly to display more information in a clearer fashion. Because events are now content pages, the sidebar widget now also links each event preview to the page for that event.

Events now include the following information:

- Title (same as page title)
- Start/end date and time
- "Doors open" time
- Location
- All other [page options]({{< static "/docs/pages/" >}})

The event list page defaults to sorting events by start date, with the latest (greatest date value) listed first.

# Semantic Changes

Another possibly breaking change in BluestNight is the assumption that section names are plural, i.e. `/events/` and `/posts/`. This should only affect the two sections used as examples, as BluestNight doesn't care about the others.

In an effort to be backwards-compatible, the home page and recent posts widget will still show content from `/post/`, though `/posts/` will be preferred if found.

The reason for this change is to try to align more closely to Hugo's convention of sections and content types being pluralized.

# Other Changes

As well as the above, the page metadata section has seen some love, with the following changes:

- Metadata labels ("Published", "Last Updated", "Estimated Reading Time") have been bolded to provide contrast between them and the metadata itself.
- "Last Updated" is only displayed if the `.Lastmod` date is different from the normal `.Date`.
- "Estimated Reading Time" received its own very special book icon.

Other miscellaneous changes:

- [Member boxes]({{< ref "docs/shortcodes/members.md" >}}) now have the option to remove the top and bottom border.
- The events sidebar widget displays "*No upcoming events*" if there are no upcoming events at build time.
- The minimum required Hugo version has been increased to [0.28](https://github.com/gohugoio/hugo/releases/tag/v0.28).
