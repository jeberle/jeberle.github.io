---
title: README
---

Instructions for getting a **Jekyll** project bootstrapped, starting from a clean machine.
The latter bits are from
[Creating your site](https://docs.github.com/en/pages/setting-up-a-github-pages-site-with-jekyll/creating-a-github-pages-site-with-jekyll#creating-your-site)
on GitHub.

#### Install Up-to-date Ruby

```shell
brew uses --installed ruby  # macvim requires ruby, otherwise...
brew install ruby

vim ~/.bashrc
# punch /usr/local/opt/ruby/bin in before /usr/bin
PATH=/usr/local/bin:/usr/local/opt/ruby/bin:/usr/bin:/bin:/usr/sbin:/sbin:/opt/X11/bin:/Library/Apple/usr/bin

. ~/.bashrc
type gem ruby
```

#### Install Bundler & Jekyll

```shell
gem install bundler jekyll
```

#### Create Jekyll Project

```shell
cd some-dir-that-might-already-have-crap-in-it
jekyll new --skip-bundle --force .
```

#### Edit `Gemfile` before downloading Gems

These changes are for GitHub Pages. The current version of `github-pages` is at [Ruby Gems](https://rubygems.org/gems/github-pages).

```yaml
#gem "jekyll", "~> 4.3.2"
gem "github-pages", "~> 228", group: :jekyll_plugins
```

```shell
bundle install
```

#### Edit `_config.yml`

Here, making an explicit reference to the unspecified theme "primer" used by GitHub Pages.

```yaml
remote_theme: pages-themes/primer@v0.6.0
plugins:
  - jekyll-feed
```

#### Install & Run Webserver

```shell
bundle add webrick
bundle exec jekyll serve --livereload
```

