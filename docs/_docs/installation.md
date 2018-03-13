---
title: Installation
description: Official guide to install Jekyll on macOS, GNU/Linux or Windows.
permalink: /docs/installation/
---

Installing Jekyll should be straight-forward if all requirements are met.

- [Install on macOS](#macOS)
- [Install on GNU/Linux](#Linux)
- [Install on Windows](../windows/)

## Install on macOS {#macOS}

We only cover latest macOS High Sierra 10.13 here, who ships a new Ruby version, older systems will need to install Homebrew, see below.

First, you need to [install Xcode from the AppStore](https://itunes.apple.com/fr/app/xcode/id497799835?mt=12). Then to install the command-line tools, open a terminal and run:

```sh
xcode-select --install
```

Check the pre-installed ruby and [RubyGems](https://rubygems.org/pages/download) versions:

```sh
ruby -v
2.3.3
gem --version
2.7.6
```

Great, let's install Jekyll, we'll also need bundler to help us handle plugins and themes:

```sh
gem install bundler jekyll
```

You're ready to go, either by installing our default jekyll blog theme with `jekyll new my-jekyll-website` or by starting from scratch:

```sh
mkdir my-jekyll-website
cd my-jekyll-website

# Create a Gemfile
bundle init

# Add Jekyll
bundle add jekyll

# Install gems
bundle install
```

From there you can either use a [theme](../themes/) or create your own.

### Install via Homebrew

You can install the latest version of Ruby via [Homebrew](https://brew.sh) a handy package manager for macOS.

```sh
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
brew install ruby
```

### Install Rbenv

Developers should use [rbenv](https://github.com/rbenv/rbenv) to handle multiple ruby environnements

```
brew install rbenv ruby-build
```

Now we can install Ruby

brew install rbenv ruby-build

## Requirements

Before you start, make sure your system has the following:

- [Ruby](https://www.ruby-lang.org/en/downloads/) version 2.2.5 or above, including all development headers (ruby installation can be checked by running `ruby -v`)
- [RubyGems](https://rubygems.org/pages/download) (which you can check by running `gem -v`)
- [GCC](https://gcc.gnu.org/install/) and [Make](https://www.gnu.org/software/make/) (in case your system doesn't have them installed, which you can check by running `gcc -v`,`g++ -v`  and `make -v` in your system's command line interface)

## Install on GNU/Linux {#Linux}

development headers can be checked on Ubuntu by running `apt list --installed  ruby-dev`

<div class="note info">
  <h5>Problems installing Jekyll?</h5>
  <p>
    Check out the <a href="../troubleshooting/">troubleshooting</a> page or
    <a href="https://talk.jekyllrb.com">ask for help on our forum</a>.
  </p>
</div>

<div class="note info">
  <h5>Running Jekyll on Windows</h5>
  <p>
    While Windows is not officially supported, it is possible to get Jekyll running
    on Windows. Special instructions can be found on our
    <a href="../windows/#installation">Windows-specific docs page</a>.
  </p>
</div>

To upgrade to latest Rubygems, run:

```
gem update --system
```

## Pre-releases

In order to install a pre-release, make sure you have all the requirements
installed properly and run:

```sh
gem install jekyll --pre
```

This will install the latest pre-release. If you want a particular pre-release,
use the `-v` switch to indicate the version you'd like to install:

```sh
gem install jekyll -v '2.0.0.alpha.1'
```

If you'd like to install a development version of Jekyll, the process is a bit
more involved. This gives you the advantage of having the latest and greatest,
but may be unstable.

```sh
git clone git://github.com/jekyll/jekyll.git
cd jekyll
script/bootstrap
bundle exec rake build
ls pkg/*.gem | head -n 1 | xargs gem install -l
```

## Already Have Jekyll?

Before you start developing with Jekyll, you may want to check that you're up to date with the latest version. To find your version of Jekyll, run one of these commands:

```sh
jekyll --version
gem list jekyll
```

You can also use [RubyGems](https://rubygems.org/gems/jekyll) to find the current versioning of any gem. But you can also use the `gem` command line tool:

```sh
gem search jekyll --remote
```

and you'll search for just the name `jekyll`, and in brackets will be latest version. Another way to check if you have the latest version is to run the command `gem outdated`. This will provide a list of all the gems on your system that need to be updated. If you aren't running the latest version, run this command:

```sh
bundle update jekyll
```

Alternatively, if you don't have Bundler installed run:

```sh
gem update jekyll
```

Please refer to our [upgrading section](../upgrading/) for major updates and detailed instructions.

Now that you’ve got everything up-to-date and installed, let’s get to work!
