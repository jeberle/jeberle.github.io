---
title: README
---

Instructions for getting a [Jekyll](https://jekyllrb.com/docs/) project bootstrapped, starting from a clean machine.

See also:
[Creating your site](https://docs.github.com/en/pages/setting-up-a-github-pages-site-with-jekyll/creating-a-github-pages-site-with-jekyll#creating-your-site)
on GitHub.

#### Install Up-to-date Ruby

```shell
brew install ruby
```

#### Update `PATH` Variable

Add `/usr/local/opt/ruby/bin` before `/usr/bin`

```shell
PATH=/usr/local/bin:/usr/local/opt/ruby/bin:/usr/bin:/bin:/usr/sbin:/sbin:/opt/X11/bin:/Library/Apple/usr/bin
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
gem "github-pages", "~> 228", group: :jekyll_plugins
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
bundle exec jekyll serve --livereload
```

