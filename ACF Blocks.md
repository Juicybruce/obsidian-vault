Directory structure is:
```
Theme Root > Blocks > <block name> > block.json and <block name>.php
```

`<block name>.php` is the template that will be rendered in both admin (with additional WordPress markup) and in `the_content()` 

`block.json` is where the block is defined and its properties set.

See the [ACF Blocks Documentation](https://www.advancedcustomfields.com/resources/acf-blocks-key-concepts/#elements-of-acf-blocks) for more information generally, and [create your first block](https://www.advancedcustomfields.com/resources/create-your-first-acf-block/#registering-blocks-with-blockjson) for specifics on config

See [DECYP for an example](https://github.com/ionata/wp-theme-decyp/blob/9b1e84994f42e319d7cd860f32e4d3813765e3df/blocks/banner/banner.php#L1), but good idea to:
1. Have placeholder data for the fields in the admin as instructions:
```
if ( is_admin() ) { 
	$title = $title ?: __('Title Goes Here', 'basetheme');
	$description = $description ?: __('Lorem ipsum d.', 'basetheme'); 
}
```
2. Apply various classes, including ones specific to the admin (to avoid weird styling conflicts)
```
$classes = array(
	'block-banner',
	'block-banner--wp',
	'block-banner--'.$orientation,
	'block-banner--'.$size,
);

if ( is_admin() ) {
	$classes[] = 'block-banner--admin';
}

if ( !empty( $block['className'] ) ) {
	$classes = array_merge( $classes, explode( ' ', $block['className'] ) );
}
```

The blocks then need to be registered within `includes/acf.php`, eg:
```
function register_acf_blocks() {
	register_block_type(THEME_DIR . '/blocks/banner');
}
add_action( 'init', 'register_acf_blocks' );
```

##### Block will now be able to be set within a field group 

This will allow you to set the custom fields you would like to have appear in the block

##### CSS for blocks needs to be seperate
This is done by keeping your `gutenberg.scss` in `/static/scss`, compiling it to `static/css` 
and enqueuing those style-sheets separately  in `includes/scripts.php`, eg:
```
// Gutenberg CSS

add_action('enqueue_block_assets', function() {
	$gutenberg = THEME_DIR . '/static/css/gutenberg.css';
	$gutenberg_time = filemtime($gutenberg);
	wp_enqueue_style( 'custom-gutenberg', THEME_STATIC . '/css/gutenberg.css' [] ,$gutenberg_time );
});
```

This requires some additional config in the builder/watcher, by adding postcss and looping it into your dev/build scripts in package.json:
```
"scripts": {
	"dev": "concurrently --kill-others \"npm run vite:dev\" \"npm run browsersync\" \"sass --watch --update --style=expanded static/scss:static/css\"",
	"build": "concurrently \"vite build\" \"postcss static/css/*.css -m -r\""
},
...
"devDependencies": {
	"postcss-cli": "^10.1.0",
	"postcss-preset-env": "^8.5.1",
}
```

You will also need a postcss config at your theme root:
```
const postcssPresetEnv = require('postcss-preset-env');
module.exports = {
	plugins: [postcssPresetEnv(/* pluginOptions */)],
};
```