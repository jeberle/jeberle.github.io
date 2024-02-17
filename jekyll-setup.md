---
title: Jekyll Setup
---

Instructions for getting a [Jekyll](https://jekyllrb.com/docs/) project bootstrapped, starting from a clean machine.

See also:
[Creating your site](https://docs.github.com/en/pages/setting-up-a-github-pages-site-with-jekyll/creating-a-github-pages-site-with-jekyll#creating-your-site)
on GitHub.

#### Install Specific Ruby Version (3.2)

```shell
brew install ruby@3.2
```

#### Update `PATH` Variable

Add `/usr/local/opt/ruby@3.2/bin` and `/usr/local/lib/ruby/gems/3.2.0/bin` before `/usr/bin`

```shell
rbin=/usr/local/opt/ruby@3.2/bin
gbin=/usr/local/lib/ruby/gems/3.2.0/bin
PATH=/usr/local/bin:$rbin:$gbin:/usr/bin:/bin:/usr/sbin:/sbin:/opt/X11/bin:/Library/Apple/usr/bin
```

```shell
. ~/.bashrc
type gem ruby
```

#### Install Bundler & Jekyll

```shell
gem install bundler jekyll
```

#### Create Jekyll Project

- `--skip-bundle` to postpone downloading Gems
- `--force` to overwrite existing files w/ same name as source
- `.` to install to current dir

```shell
cd some-dir
jekyll new --skip-bundle --force .
```

#### Edit `Gemfile`

These changes are for GitHub Pages. The current version of `github-pages` is at
[Ruby Gems](https://rubygems.org/gems/github-pages).

```yaml
#gem "jekyll", "~> 4.3.2"
gem "github-pages", "~> 231", group: :jekyll_plugins
```

#### Download Gems

```shell
bundle install
```

#### Edit `_config.yml`

Here, making an explicit reference to the unspecified theme "primer" used by GitHub Pages.
Also setting `title`.

```yaml
title: "Some Website" # defaults to project dir name, seen in <title> and page header
remote_theme: pages-themes/primer@v0.6.0
plugins:
  - jekyll-feed
```

#### Install & Run Webserver

```shell
bundle add webrick
rlib=/usr/local/opt/ruby@3.2/lib
DYLD_LIBRARY_PATH=$rlib bundle exec jekyll serve --livereload
```

#### Resolve GitHub Metadata Access

Make sure the following vars in `_config.yml` are set:

```yaml
# set these to deactivate metadata lookup
github:      []
title:       "jeberle.github.io"
description: ""
url:         "" # the base hostname & protocol for your site, e.g. http://example.com
baseurl:     "" # the subpath of your site, e.g. /blog
```

For actual lookup (and to resolve the **GitHub Auth** warning), create a GitHub token here
<https://github.com/settings/tokens>.
The only required auth is "access to public repos". Then:

```shell
export JEKYLL_GITHUB_TOKEN='<token-string>'
```

The plugin is part of github-pages and so is baked in.
<https://jekyll.github.io/github-metadata/>
