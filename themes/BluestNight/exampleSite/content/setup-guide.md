+++
title = "Setup Guide"
hide_authorbox = true
disable_comments = true
enable_toc = true
alert = "Have improvements you'd like to see in this guide? File an [issue](https://gitlab.com/BluestNight/website/issues) and let us know!"
menu = "main"
weight = 4
+++

This article is meant to provide users with a concise guide for setting up a Hugo site to use BluestNight. This guide replaces the Hugo setup guide, though it refers to Hugo documentation throughout for things not specific to BluestNight.

# Step 1: Install Dependencies

You will need [Hugo](https://gohugo.io/getting-started/installing) and optionally [Git](https://git-scm.com/downloads). If you would prefer not to use Git, links will be provided to download a zipped folder containing the files.

The following pages of the Hugo documentation are important to creating your site but are not specific to BluestNight. Read through at least those pages if you don't know how Hugo works, then continue to Step 2.

- [Basic Usage](https://gohugo.io/getting-started/usage/)
- [Directory Structure](https://gohugo.io/getting-started/directory-structure/)
- [Configuration](https://gohugo.io/getting-started/configuration/)
- [Front Matter](https://gohugo.io/content-management/front-matter/)
- [Content Sections](https://gohugo.io/content-management/sections/)
- [Menus](https://gohugo.io/content-management/menus/)
- [Static Files](https://gohugo.io/content-management/static-files/)

# Step 2: Copy the Site Template

Download the BluestNight site template onto your computer using the below Git command or by downloading this [zip file](https://gitlab.com/BluestNight/site-template/repository/master/archive.zip) and extracting it to wherever you want the site to be kept.

If you use the below commands, be sure to replace the example folder paths with the path to the *existing* folder that will hold the folder containing the site's source code (e.g. `~/Documents/websites/`). Also replace `example.com` with the name you want to give the new folder: the domain name of the site is a good candidate.


## Linux/Mac OS X/Git Bash for Windows
```bash
cd $HOME/hugo-sites/
git clone --depth 1 https://gitlab.com/BluestNight/site-template example.com
cd example.com
git submodule update --init
rm -rf .git
```

## Windows
```
cd %HOMEPATH%/hugo-sites/
git clone --depth 1 https://gitlab.com/BluestNight/site-template example.com
cd example.com
git submodule update --init
rmdir /S /Q .git
```

# Step 3: Modify the Site's config.toml

Open the `config.toml` file in the root of the new folder using your favorite text editor. The file itself is well-documented, so take the time to go through the various options and change what you want. At minimum, change the following values:

- `title`
- `baseurl`
- `tagline`
- `description`

# Step 4: Add Content

Use the `hugo new` command to create a new page(s) on your site. For example:

```bash
hugo new posts/hello-world.md
```

You can modify the front matter of the page and add content using [Markdown](https://www.markdownguide.org/basic-syntax). If you'd like to see what customization BluestNight offers per page, see the [documentation]({{< static "docs/pages" >}}).

# Step 5: Preview Your Site

To preview the changes you're making to your site, use the following command:

```bash
hugo server --disableFastRender --buildDrafts
```

Building drafts is useful when you are working on new content that you aren't ready to publish but want to preview.

You will also want to disable Fast Render mode because it has been known to break things when *rebuilding* a site using BluestNight.

# Step 6: Make More Changes

BluestNight offers a lot of features, so take a look through the [documentation]({{< static "docs" >}}) and see what looks useful to you. Add more pages using `hugo new` and flesh out your website.

# Step 7: Deploy

The Hugo documentation provides some good [guides to deploying](https://gohugo.io/hosting-and-deployment/) on various systems. You can also build your site locally and upload the contents of `public/` to a server using FTP or another file transfer protocol.