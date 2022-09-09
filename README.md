# AIM RSF Internal Events

This repository houses the AIM RSF's internal events page hosted by GitHub pages (and built with Hugo). The events page is currently part of a user test for outreach efforts across the AIM Consortia and will be moved into a private repository once this stage of the project has completed.

### **Maintainers**

This repository is jointly developed and maintained by the AIM RSF Operations Team led by Programme Manager Dave Chapman with support from Sophia Batchelor and Eirini Zormpa under the Tools, Practices and Systems, and Health and Medicine Research Programmes at The Alan Turing Institute

### Contributing

If you want to contribute to the content or maintenance of this site, please refer to the Contributing Guidelines and Code of Conduct.


## Repository Overview

* Pages and page content is hosted in `content/blog`
* RSF Theme information and other banners are hosted in `data`
* GitHub Pages submodules are managed in `.github/workflows/cd.yml` as the site is deployed using GitHub Actions
* To edit font, menu items, or colour scheme please refer to the `config.toml` file

### Installation Guide

You need to have [Hugo](https://gohugo.io/) installed Please follow the official [installation guide](https://gohugo.io/getting-started/installing/) and ⚠️  **note that Hugo Extended is required!**⚠️  

For more information on geting started with Hugo and GitHub Pages, please refer to [this tutorial](https://hackmd.io/@sgibson91/BlogSitesHugoGitHubPages) by Dr Sarah Gibson. 

### Updating the theme

#### Logo

You can edit the logo from the `config.toml`

```toml
# config.toml

  [params.logo]
    mobile = "images/logo/logo-mobile.svg"
    mobile_height = "36px"
    desktop = "images/logo/logo.svg"
    desktop_height = "36px"
    alt = "Serif - A Hugo Business Theme"
```

#### Fonts

This theme uses Google fonts. You can change the google font in the `config.toml` - These fonts are injected into the `style.scss` as SCSS variables.

```toml
# config.toml

  [params.fonts]
    # sets the google font link in layouts/partials/google-fonts.html
    google_fonts = 'https://fonts.googleapis.com/css2?family=Playfair+Display:wght@600&family=Source+Sans+Pro:wght@400;700&display=swap'
    heading = "Playfair Display"
    base = "Source Sans Pro"
```

### Colors

You can edit the themes main colors in the `config.toml`. These colors are injected into the `style.scss` as SCSS variables.

```toml
#config.toml

  [params.colors]
    primary = "#f24088"
    black = "#2f2f41"
    white = "#ffffff"
    white_offset = "#f6f7ff"
    grey = "#5C5A5A"
```

### Intro Image

List pages such as the homepage, services and team can have a Intro image.

```yaml
# content/_index.md
---
intro_image: "https://source.unsplash.com/wOGhHamMqLc"
intro_image_absolute: false
intro_image_hide_on_mobile: true
---
```

While this themes default content uses illustrations, its easy to change the image to a photo and it will still look great.

the front-matter field `intro_image_absolute: true` let's illustrations "break out" (in CSS terms, it uses `position: absolute`)
 of the grid and is an intended stylistic effect. When using photos or
normal images it's recommended to set this field to false and the photo
will align with the grid. See `content/team/_index.md` for an example.

#### Meta tags

A pages `<title>` is generated from the front-matter `meta_title` else it will use the `title` property. This allows you to have a different heading on the page to what is shown in the SEO title. See `content/_index.md` for an example.

The meta description field is generated from the front-matter `description`

OG meta data for Facebook and Twitter is also generated on a per page basis. The `image` field is used for the og:image for Twitter and Facebook.

You can configure og meta data global settings in the config.

```toml
# config.toml

  [params.seo]
    meta_twitter_site = "@zerostaticio"
    meta_twitter_creator = "@zerostaticio"
    meta_og_image = "https://www.zerostatic.io/theme/hugo-serif/hugo-serif-screenshot.pn
```

To pull in any upstream changes to the theme being used as a git submodule, run the following.

```bash
git submodule update --remote --merge
```

## Attribution

Thank you to the creators and maintainers of the [Hugo Serif](https://github.com/zerostaticthemes/hugo-serif-theme) theme.
