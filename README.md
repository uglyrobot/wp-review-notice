<p align="center">
<a href="http://duckdev.com" target="_blank">
    <img width="200px" src="https://duckdev.com/wp-content/uploads/2020/12/cropped-duckdev-logo-mid.png">
</a>
</p>

# WP Review Notice
Simple library class to gently ask for a wp.org plugin review after a few days of plugin usage.

## Installation
WP Review Notice can be installed using composer:

```
$ composer require duckdev/wp-review-notice
```

## Usage 📖

### Initialize

Initialize one notice per plugin.
```php
// Setup notice.
$notice = \DuckDev\Reviews\Notice::get(
	$slug, // Plugin slug on wp.org (eg: hello-dolly).
	$name, // Plugin name (eg: Hello Dolly).
	$options // Notice options.
);

// Render notice.
$notice->render();
```
### Options
You can customize the notice behaviour using options.

| Option  | Type | Description |
| ------- | ---- | ----------- |
| `days` | int | No. of days after the review is shown.  |
| `screens` | array| WordPress admin page screen IDs to show notice. If you leave this empty the notice will be added to add admin pages. Strongly recommended to use this option to limit the review notices only within your plugin's admin pages, especially if you are showing notice using `admin_notices` action. |
| `cap` | string | WordPres user capability to show notice to. Notice will be visible only to user with this capability. Also only users with this capability can dismiss/extend notice. |
| `classes` | array | Additional class names for notice. |
| `domain` | string | Text domain string for internationalization. |
| `prefix` | string | To override plugin option and other key prefixes. By default it's plugin slug with dashes replaces with underscores. |

### Credits
Author - [Joel James](https://duckdev.com)