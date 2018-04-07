---
layout: post
title: "A Post with Images"
description: "Examples and code for displaying images in posts."
tags: [sample post, images, test]
date: 2013-05-22
---

Here are some examples of what a post with images might look like. If you want to display two or three images next to each other responsively use `figure` with the appropriate `class`. Each instance of `figure` is auto-numbered and displayed in the caption.

## Figures (for images or video)

### One Up

<figure>
	<a href="//farm9.staticflickr.com/8426/7758832526_cc8f681e48_b.jpg"><img src="//farm9.staticflickr.com/8426/7758832526_cc8f681e48_c.jpg" alt=""></a>
	<figcaption><a href="//www.flickr.com/photos/80901381@N04/7758832526/" title="Morning Fog Emerging From Trees by A Guy Taking Pictures, on Flickr">Morning Fog Emerging From Trees by A Guy Taking Pictures, on Flickr</a>.</figcaption>
</figure>

### Two Up

Apply the `half` class like so to display two images side by side that share the same caption.

```html
<figure class="half">
	<img src="/images/image-filename-1.jpg" alt="">
	<img src="/images/image-filename-2.jpg" alt="">
	<figcaption>Caption describing these two images.</figcaption>
</figure>
```

And you'll get something that looks like this:

<figure class="half">
	<a href="//placehold.it/1200x600.jpg"><img src="//placehold.it/600x300.jpg" alt=""></a>
	<a href="//placehold.it/1200x600.jpg"><img src="//placehold.it/600x300.jpg" alt=""></a>
	<img src="//placehold.it/600x300.jpg" alt="">
	<img src="//placehold.it/600x300.jpg" alt="">
	<figcaption>Two images.</figcaption>
</figure>

### Three Up

Apply the `third` class like so to display three images side by side that share the same caption.

```html
<figure class="third">
	<a href="//placehold.it/1200x600.jpg"><img src="//placehold.it/600x300.jpg" alt=""></a>
	<a href="//placehold.it/1200x600.jpg"><img src="//placehold.it/600x300.jpg" alt=""></a>
	<a href="//placehold.it/1200x600.jpg"><img src="//placehold.it/600x300.jpg" alt=""></a>
	<figcaption>Caption describing these three images.</figcaption>
</figure>
```

And you'll get something that looks like this:

<figure class="third">
	<a href="//placehold.it/1200x600.jpg"><img src="//placehold.it/600x300.jpg" alt=""></a>
	<a href="//placehold.it/1200x600.jpg"><img src="//placehold.it/600x300.jpg" alt=""></a>
	<a href="//placehold.it/1200x600.jpg"><img src="//placehold.it/600x300.jpg" alt=""></a>
	<a href="//placehold.it/1200x600.jpg"><img src="//placehold.it/600x300.jpg" alt=""></a>
	<a href="//placehold.it/1200x600.jpg"><img src="//placehold.it/600x300.jpg" alt=""></a>
	<a href="//placehold.it/1200x600.jpg"><img src="//placehold.it/600x300.jpg" alt=""></a>
	<figcaption>Three images.</figcaption>
</figure>
