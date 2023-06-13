# Docker Github Pages Starter

Uses Minimal Mistakes remote theme starter and adds docker support.

**Warning Notice:** I fumbled through these steps and they are not refined, the theme is awesome and well supported, however, I run a python app with a MongoDB database and this template speeds up my developement. Feedback to improve welcome!
{: .notice--danger}

Click [**Use this template**](https://github.com/mrwayneo/docker-github-pages-starter/generate) 

Based on [Minimal Mistakes Jekyll theme](https://github.com/mmistakes/minimal-mistakes).

Contains basic configuration to get you a site with:

- Sample posts.
- Sample top navigation.
- Sample author sidebar with social links.
- Sample footer links.
- Paginated home page.
- Archive pages for posts grouped by year, category, and tag.
- Sample about page.
- Sample 404 page.
- Site wide search.
Optional:
- Docker support/setup for local developement environment
- Python application container
- MongoDB container
- Jekyll container

Replace sample content with your own and [configure as necessary](https://mmistakes.github.io/minimal-mistakes/docs/configuration/).

## Optional: Docker Developement Environment Installation

If you don't wish to run locally using Docker containers for python application, MongoDB and Jekyll you can ignore or remove the following files:

```
<PROJECT-NAME>
|-- .env
|-- .bashrc
|-- docker-compose.yaml
|-- Dockerfile
|-- requirements.txt
```

Alternatively, to setup a developement environment locally:

1. Run `git clone https://[USERNAME]:[NEW TOKEN]@github.com/[USERNAME]/[REPO].git`
3. Edit .env file and update `COMPOSE_PROJECT_NAME=[NEW PROJECT]`
4. Edit the docker-compose.yaml file and update the ports to preferred ports on your system, eg. `4099:4000`
5. Run `docker compose up`
6. Navigate to localhost:4099 changing the port number to your preferred port number.

## Setup splash page as homepage

1. Delete index.html
2. Add home.md to `_pages` folder and fill with the content from [Minimal Mistakes Splash content](https://github.com/mmistakes/minimal-mistakes/blob/master/docs/_pages/splash-page.md) and customise accordingly.

## Optional features (I used):

### [Added logo to masthead](https://mmistakes.github.io/minimal-mistakes/docs/configuration/#site-masthead-logo)

### [Changed styling (CSS/SCSS) of masthead](https://mmistakes.github.io/minimal-mistakes/docs/stylesheets/)

I wanted the avatar to appear like it was looking over the splash page. 

1. Copy [main.scss](https://github.com/mmistakes/minimal-mistakes/blob/master/assets/css/main.scss) to PROJECT-NAME/assets/css/main.scss.
2. Add CSS styling below the @import statements.

Change padding of the masthead inner wrap and avatar size to give the desired avatar effect.
```
@charset "utf-8";

@import "minimal-mistakes/skins/{{ site.minimal_mistakes_skin | default: 'default' }}"; // skin
@import "minimal-mistakes"; // main partials

.masthead {

  &__inner-wrap {
    padding: 0 1em 0 1em;
  }
}

.site-logo img {
  max-height: 2.5rem;
}
```

### Display collection on home full width:

Added CSS/SCSS

```
.wide2 {
  .page {
    float: left;
    width: 100%;
    @include breakpoint($large) {
      padding-left: 0;
    }

    @include breakpoint($x-large) {
      padding-left: 0;
    }
  }

  .page__related {
    @include breakpoint($large) {
      padding-left: 0;
    }

    @include breakpoint($x-large) {
      padding-left: 0;
    }
  }
}
```

---

## Troubleshooting

If you have a question about using Jekyll, start a discussion on the [Jekyll Forum](https://talk.jekyllrb.com/) or [StackOverflow](https://stackoverflow.com/questions/tagged/jekyll). Other resources:

- [Ruby 101](https://jekyllrb.com/docs/ruby-101/)
- [Setting up a Jekyll site with GitHub Pages](https://jekyllrb.com/docs/github-pages/)
- [Configuring GitHub Metadata](https://github.com/jekyll/github-metadata/blob/master/docs/configuration.md#configuration) to work properly when developing locally and avoid `No GitHub API authentication could be found. Some fields may be missing or have incorrect data.` warnings.
