# Contributing to Compute Freely

This site is powered by [Jekyll](https://jekyllrb.com/), and its basic structure is a set of fixed pages (Home, About, Switching, etc.), along with some dynamically generated list pages like Tags and Categories, and then the bulk of the content lies on individual posts, one per distribution. See [Directory Structure](https://jekyllrb.com/docs/structure/) in the Jekyll docs to learn more about this setup.

This blog-like approach for the distribution pages allows making use of Jekyll's features for dynamic, dated content, including built-in support for metadata like the publication date and authors of the text, showing a banner for content that is potentially outdated, etc.

## Submitting distributions

Submitting a new distribution page is simply a matter of writing a new post and adding it to the `_posts` folder. When writing a post for a distribution you would like to submit, you are free to author the text yourself (making sure to keep a neutral and objective tone); however, but if you choose to use information from the project's website to fill out the post, paraphrase the content instead of copying straight from it.

For your convenience, a template post is included in the `_drafts` folder.

### Metadata

Each post has a [frontmatter](https://jekyllrb.com/docs/front-matter/) section that contains [YAML](https://yaml.org/)-formatted metadata for the post and about the distribution in general. This information shows up as  on the individual pages for each. Here's an example from the post for Ubuntu.

```yaml
layout: distro
author: "Sam Hewitt"
title: "Ubuntu"
date: "2017-03-02"
updated: "2020-09-26"
updater: "Tomasz Pocztowski"
logo: "ubuntu"
image: "ubuntu-20.04.png"
caption: "ubuntu 20.04 with the GNOME desktop"
tags: [desktop, server]
category: [beginner]
notes:
  homepage: https://ubuntu.com/
  version: "20.04"
  based-on: ["Debian"]
  desktops: [GNOME]
  install: graphical
  developers:
    - name: Canonical
      url: https://canonical.com/
    - name: Ubuntu Community
      url: https://community.ubuntu.com/
```

#### Publication metadata

The first half of the frontmatter contains publishing and categorization information for the post.

- `layout` (always `distro`) is the page layout for Jekyll
- `title` is the distribution name
- `date` is the date of publication of the post (i.e. addition of the distribution to this project)
- `updated` is the date of the last update to the post (e.g. changing the version, fixing a typo, etc.)
- `updater` is the name of the person who last updated the post
- `logo` is the file name of the logo that you provide (minus the extension)
- `image` is the filename of the screenshot you provide (including the extension)
- `caption` is an optional description of the screenshot
- `tags` is an array of tags for the post. These should be limited to things like its primary purpose (e.g. `server`, `desktop`, `enterprise`)
- `category` is a one-word estimation of the distribution's approachability (`beginner`, `intermediate` or `advanced`)

#### Distribution metadata

The `notes` section contains pertinent info about the distribution itself that shows up in the “Notes” section on each post.

- `homepage` is the complete url of a distribution's homepage
- `version` is the current version at the time of publication
- `based-on` is a list of distributions that this one is based on (if any)
- `desktops` is an array of all default desktop environments provided by the distribution
- `install` is the mode of installation — either “graphical”, “command line” or “live”
- `developers` is the name (and optionally an URL) of the primary developer or developers of the distribution

### Including image assets

For a submission to be included you must also include a project's logo and a screenshot.

An acceptable screenshot must:

- be of a fresh installation, no user-modifications or changes
- be of the desktop, do not have any windows, menus, etc. open
- be of at least 720p resolution
- follow the name convention of the other included screenshots, that is `<distro-name>-<version>.png`

An acceptable version of the project logo must:

- be of the distribution icon, not the wordmark
- be in SVG format, a PNG or other file format will not display
- follow the name convention of the other included logos, that is `<distro-name>.svg`
- be 200x200 pixels and the logo is at most 160x160 within that

## Updating an existing post

If you're simply updating an existing post, make the changes to the post as necessary but don't remove the original author's name from `author` or change the `date:` field (this is to keep track of the original); simply add the following lines:

```yaml
updated: "YYYY-MM-DD"
updater: "Your Name"
```

Then rename the post file with the `updated:` date.

## Other contributions

Overall improvements to the site are gladly accepted as well and can be made via a general pull request.

To make style or structure changes, it's best to have a basic understanding of how Jekyll works. The [Jekyll documentation](https://jekyllrb.com/docs/) is generally pretty comprehensive and readable, so it will probably be a useful resource for those wanting to do these types of contributions.
