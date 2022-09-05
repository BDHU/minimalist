# The Minimalist theme

*Minimalist is a Jekyll theme, inspired by the [Minimal](https://github.com/pages-themes/minimal) theme from GitHub. You can [preview the theme to see what it looks like](http://bdhu.github.io/minimalist), or even [use it today](#usage).*

![Demo of Minimalist](https://raw.githubusercontent.com/BDHU/minimalist/main/minimalist.png)

## Usage

### Docker

The simplest way is to use a Docker container. For Docker installation instructions, please refer to the offical Docker [docs](https://docs.docker.com/engine/install/). After successful installation, simply execute:

```bash
./deploy.sh
```

### Other Methods

To use the Minimalist theme:

1. Add the following line to your Gemfile

```ruby
gem "jekyll-remote-theme"
```

then run `bundle install` to install the plugin.

2. Add the following to your site's `_config.yml` to activate the plugin:

```yml
plugins:
  - jekyll-remote-theme
```

Note: If you are using a Jekyll version less than 3.5.0, use the `gems` key instead of `plugins`.

3. Add the following line to your `config.yml` to use the theme

```yml
remote_theme: BDHU/minimalist
```

then running `bundle exec jekyll serve` for local deployment. Here is a [demo](https://github.com/BDHU/bdhu.github.io) using this theme.

An example `_config.yml` file can be found [here](https://github.com/BDHU/bdhu.github.io/blob/master/_config.yml). More info can be found at [Jekyll Remote Theme](https://github.com/benbalter/jekyll-remote-theme).

## Customizing

### Configuration variables

Minimalist will respect the following variables, if set in your site's `_config.yml`:

```yml
title: [The title of your site]
description: [A short description of your site's purpose]
```

Additionally, you may choose to set the following optional variables:

```yml
google_analytics: [Your Google Analytics tracking ID]
```

Choose light, dark, or automatically adjusting theme based on system theme:

```yml
color-scheme: auto/light/dark
```

Specify logo for the website:

```yml
logo: /assets/img/<logo_file>
```

Enable favicon by putting a `favicon.ico` in the repo's root directory and add the following line in `config.yml`:

```yml
favicon: true
```

### Customizing Sidebar

You can define a list of platforms that are linked from the sidebar in `_config.yml`:

```yml
sidebar:
  - name: Google Scholar
    icon: <svg xmlns="http://www.w3.org/2000/svg" aria-hidden="true" role="img" style="vertical-align:-0.125em;" width="1em" height="1em" preserveAspectRatio="xMidYMid meet" viewBox="0 0 24 24"><path d="M5.242 13.769L0 9.5L12 0l12 9.5l-5.242 4.269C17.548 11.249 14.978 9.5 12 9.5c-2.977 0-5.548 1.748-6.758 4.269zM12 10a7 7 0 1 0 0 14a7 7 0 0 0 0-14z" fill="currentColor"/></svg>
    link: https://scholar.google.com/citations?user=zR6afi8AAAAJ
  - name: GitHub
    icon: <i class="fa-brands fa-github"></i>
    link: https://github.com/BDHU
  - ...
```

For further customization of the sidebar, go to [sidebar.html](https://github.com/BDHU/minimalist/blob/main/_includes/sidebar.html) in this repo and modify it however you like. The [link-mobile.html](https://github.com/BDHU/minimalist/blob/main/_includes/links-mobile.html) customizes the sidebar's look on mobile devices. This example uses fonts from [font awesome](https://fontawesome.com) and [Iconify](https://iconify.design/). Feel free to explore/find other sources.

### Stylesheet

If you'd like to add your own custom styles:

1. Create a file called `/assets/css/style.scss` in your site
2. Add the following content to the top of the file, exactly as shown:

    ```scss
    ---
    ---

    @import "{{ site.theme }}";
    ```

3. Add any custom CSS (or Sass, including imports) you'd like immediately after the `@import` line

*Note: If you'd like to change the theme's Sass variables, you must set new values before the `@import` line in your stylesheet.*

### Layouts

If you'd like to change the theme's HTML layout:

1. For some changes such as a custom `favicon`, you can add custom files in your local `_includes` folder. The files [provided with the theme](https://github.com/BDHU/minimalist/tree/master/_includes) provide a starting point and are included by the [original layout template](https://github.com/BDHU/minimalist/blob/master/_layouts/default.html).
2. For more extensive changes, [copy the original template](https://github.com/BDHU/minimalist/blob/master/_layouts/default.html) from the theme's repository<br/>(*Pro-tip: click "raw" to make copying easier*)
3. Create a file called `/_layouts/default.html` in your site
4. Paste the default layout content copied in the first step
5. Customize the layout as you'd like

For example, this [repository](https://github.com/BDHU/bdhu.github.io) shows how customizations are made on the original theme.

### Customizing Google Analytics code

Google has released several iterations to their Google Analytics code over the years since this theme was first created. If you would like to take advantage of the latest code, paste it into `_includes/head-custom-google-analytics.html` in your Jekyll site.

## Previewing the theme locally

If you'd like to preview the theme locally (for example, in the process of proposing a change):

1. Clone down the theme's repository (`git clone https://github.com/BDHU/minimalist`)
2. `cd` into the theme's directory
3. Run `script/bootstrap` to install the necessary dependencies
4. Run `bundle exec jekyll serve` to start the preview server
5. Visit [`localhost:4000`](http://localhost:4000) in your browser to preview the theme

## Running tests

The theme contains a minimal test suite, to ensure a site with the theme would build successfully. To run the tests, simply run `script/cibuild`. You'll need to run `script/bootstrap` once before the test script will work.

## Contributors

Special thanks to [@godalming123](https://github.com/godalming123) for adding dark mode support. Also thank [@solvaholic](https://github.com/solvaholic), [@tildehacker](https://github.com/tildehacker), and other contributors for making multiple bug fixes and improvements. All contributions are welcome.
