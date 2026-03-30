# Minimaxing Theme

The **Minimaxing** Theme is for [Grav CMS](http://github.com/getgrav/grav). It's a port of [Minimaxing](https://html5up.net/minimaxing) by HTML5 UP under its [CCA 3.0 license](https://html5up.net/license).

The Grav port includes an additional [Elements page](_demo/pages/90.elements/onecolumn.md) as per many HTML5UP themes, to allow you to identify gaps in the theme's styling (spoiler: there are many).

![Minimaxing](screenshot.jpg)

# Installation

Installing the Minimaxing theme can be done in one of two ways. Our GPM (Grav Package Manager) installation method enables you to quickly and easily install the theme with a simple terminal command, while the manual method enables you to do so via a zip file.

## GPM Installation (Preferred)

The simplest way to install this theme is via the [Grav Package Manager (GPM)](http://learn.getgrav.org/advanced/grav-gpm) through your system's Terminal (also called the command line).  From the root of your Grav install type:

    bin/gpm install minimaxing

This will install the Minimaxing theme into your `/user/themes` directory within Grav. Its files can be found under `/your/site/grav/user/themes/minimaxing`.

>> This method will copy the sample pages provided in the `_demo/pages` folder to your `user/pages` folder so that the theme will work out of the box with placeholder content. The content is the same _Ipsum lorem_ content provided in the original [HTM5UP theme](https://html5up.net/minimaxing).

## Manual Installation

To install this theme, just download the zip version of this repository and unzip it under `/your/site/grav/user/themes`. Then, rename the folder to `minimaxing`. You can find these files either on [GitHub](https://github.com/hughbris/grav-theme-minimaxing) or via [GetGrav.org](http://getgrav.org/downloads/themes).

You should now have all the theme files under

    /your/site/grav/user/themes/minimaxing

>> NOTE: If you want to use and adapt the default _Ipsum lorem_ content provided with the original theme, move the contents of `_demo/pages` into your grav installations's `user/pages` directory. This will ensure that the theme templates work out of the box.

# Updating

As development for the Minimaxing theme continues, new versions may become available that add additional features and functionality, improve compatibility with newer Grav releases, and generally provide a better user experience. Updating Minimaxing is easy, and can be done through Grav's GPM system, as well as manually.

## GPM Update (Preferred)

The simplest way to update this theme is via the [Grav Package Manager (GPM)](http://learn.getgrav.org/advanced/grav-gpm). You can do this with this by navigating to the root directory of your Grav install using your system's Terminal (also called command line) and typing the following:

    bin/gpm update minimaxing

This command will check your Grav install to see if your Minimaxing theme is due for an update. If a newer release is found, you will be asked whether or not you wish to update. To continue, type `y` and hit enter. The theme will automatically update and clear Grav's cache.

## Manual Update

Manually updating Minimaxing is pretty simple. Here is what you will need to do to get this done:

* Delete the `your/site/user/themes/minimaxing` directory.
* Download the new version of the Minimaxing theme from either [GitHub](https://github.com/hughbris/grav-plugin-minimaxing) or [GetGrav.org](http://getgrav.org/downloads/themes#extras).
* Unzip the zip file in `your/site/user/themes` and rename the resulting folder to `minimaxing`.
* Clear the Grav cache. The simplest way to do this is by going to the root Grav directory in terminal and typing `bin/grav clear-cache`.

> Note: Any changes you have made to any of the files listed under this directory will also be removed and replaced by the new set. Any files located elsewhere (for example a YAML settings file placed in `user/config/themes`) will remain intact.

### Supported Page Templates

* [Sample homepage view template](templates/home.html.twig)
* [Left sidebar two-column template](templates/twocolumn1.html.twig)
* [Right sidebar two-column template](templates/twocolumn2.html.twig)
* [Single column template](templates/onecolumn.html.twig)
* [Three-column template](templates/threecolumn.html.twig)

## Deferred assets block support

[Deferred blocks were introduced in Grav 1.5.10](https://getgrav.org/blog/important-theme-updates) and **are now required by this theme**.

## Twig Autoescaping support

# Configuring

## Menu Features

### Dropdown Menu

You can enable **dropdown menu** support by enabling it in the `minimaxing.yaml` configuration file. As per usual, copy this file to your `user/config/themes/` folder (create if required) and edit there.

```yaml
dropdown:
  enabled: true
```

This will ensure that sub-pages show up as sub-menus in the navigation.

### Menu Text & Icons

Each page shows up in the menu using the title by default, however you can set what displays in the menu directly by setting an explicit `menu:` option in the page header:

```yaml
menu: My Menu
```

You can also provide an icon to show up in front of the menu item by providing an `icon:` option.  You need to use name of the FontAwesome icon without the `fa-` prefix.  Check out the full [list of current FontAwesome 4.2 icons](http://fortawesome.github.io/Font-Awesome/icons/):

```yaml
icon: bar-chart-o
```

### Custom Menu Items

By default, Grav generates the menu from the page structure.  However, there are times when you may want to add custom menu items to the end of the menu.  This is now supported in Minimaxing by creating a menu list in your `site.yaml` file.  An example of this is as follows:

```yaml
menu:
    - text: Source
      url: https://github.com/getgrav/grav
    - icon: twitter
      url: http://twitter.com/getgrav
```

The `url:` option is required, but you can provide **either** or **both** `text:` and/or `icon:`

## Source theme conformance

Thanks to some weird workarounds that hopefully don't bring me technical debt (sorry future self!), and not wanting to break any existing implementations, I've added a conformance frontmatter property to contain settings for potentially anything that might be a departure from the source HTML5UP theme.

```yaml
# theme elements that should match the source theme rather than an improved one offered in this Grav theme
conformance:
    jquery: true
```

### jQuery library

The theme is bundled with a [minified jQuery source file](https://github.com/hughbris/grav-theme-minimaxing/blob/develop/js/jquery.min.js), which is out of date but works, and which you may prefer to use instead of the [much later version still bundled as an asset group by Grav core](https://github.com/getgrav/grav/blob/afb5b02e5750f0f9c0bcc73de5d3f62947881722/system/config/system.yaml#L139).

> For the moment your site will keep working as it has been if you don't change any settings. This might change BTW, slowly slowly.

There have been some dependabot alerts about the old jQuery bundled with the source theme and with this Grav theme. I am not an expert and have not looked closely, but I _suspect_ this theme is _not vulnerable_ to these exploits. _This is not advice. Also not an invitation to anyone with nefarious intent._

The pros and cons of each option are outlined in this issue: **[Unable to update jQuery reliably for users of the debugbar](https://github.com/hughbris/grav-theme-minimaxing/issues/14)**.

This theme provides **two more options** to load whatever you like for your jQuery. The jQuery asset is added:

* in a partial template at `templates/partials/asset-jquery.html.twig` that _you can easily override in a custom theme_;
* within a Twig block called `jquery` that _you can extend inside another template_.

## Setup

If you want to set Minimaxing as the default theme, you can do so by following these steps:

* Navigate to `/your/site/grav/user/config`.
* Open the **system.yaml** file.
* Change the `theme:` setting to `theme: minimaxing`.
* Save your changes.
* Clear the Grav cache. The simplest way to do this is by going to the root Grav directory in Terminal and typing `bin/grav clear-cache`.

Once this is done, you should be able to see the new theme on the frontend. Keep in mind any customizations made to the previous theme will not be reflected as all of the theme and templating information is now being pulled from the **minimaxing** folder.

# Example

Please let me know if you would like your example listed here. It's shameless promotion.

* [Kosy K9s & Katz kennels](https://kosyk9s.co.nz)
