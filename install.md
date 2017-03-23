# Setup of these pages

Initially setup via GitHub webinterface and changed/edited markdown pages there. Later switched to a jekyll/CLI usage:

Added a Gemfile with the following content

```
    source "http://rubygems.org"
    ruby RUBY_VERSION
    # gem "jekyll", "3.4.1"
    gem "github-pages", group: :jekyll_plugins
```

(See [pages.github.com/versions](https://pages.github.com/versions/) for the current dependency versions of gems and more informations about the [github-pages](https://github.com/github/pages-gem) gem)

Added a css folder with a main.scss file

### Run locally

```
    bundle exec jekyll serve
``
This will serve the rendered site via http://127.0.0.1:4000/INTPRN/


