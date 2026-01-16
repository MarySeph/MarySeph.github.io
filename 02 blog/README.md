# Zonelots, a simple blogging framework

Zonelots is a simple script (and some HTML and CSS files) that helps you easily make a blog you can upload to static hosting like [Neocities](https://neocities.org)! It's based on [Zonelets](https://zonelets.net/) by [Marina Kittaka](https://twitter.com/even_kei), which has a great tutorial already that you should go and read first. This readme's more about the differences between Zonelets and Zonelots, and instructions on using the Zonelots framework.

**Note:** Zonelots is currently at version 2, released August 2024, which has breaking changes with version 1, last updated December 2022. I would've preferred no breaking changes, but I started on Zonelots when I had much less frontend knowledge and it shows. However, the differences between versions are mostly refactoring rather then new features, and the old version still works.

## Differences from Zonelets

Here are the main differences from Zonelets:

1. **Tagging!** You can tag posts and the tags link to an index listing all posts by tag.
2. **Header messages!** (optional) You can write a list of messages in the script, one of which will randomly appear in the header on each pageload.
3. **Post navigation!** The links to the next and previous posts have the matching post titles added. There's also a skip-link and a return-to-top link on each page.
4. **Gallery CSS!** There's some extra CSS for making image galleries that scale to the number of images you add.

## Zonelot blog guide

### How to set up your Zonelot blog

1. Go through the starting `.html` files (`index`, `about`, `archive`, `tags`, `not_found`, and the post template) and rewrite the text for your blog.
2. Go through `script.js` and edit the following (they're all near the top):
	* `latestPostsCutoff`: how many posts appear on your blog's index page
	* `messagesOn`: whether random messages from your list will appear in the page header
	* `navLinks`: links in the header pointing to the static pages (`index.html` etc.)
	* `contactLinks`: links that appear in the page footer
3. Delete the example posts in the posts folder and their data in the `posts` array.
4. Delete the example messages in the `messages` array.
5. Finally, you'll want to change the favicon file(s). See below for more info.

You're also heavily encouraged to build on the styling in `main.css`. Finally, put it up somewhere online, e.g. [Neocities](https://neocities.org).

### Updating your site

#### The cache ("Why isn't my site changing when I update the files online?")

When your browser gets a web page from the internet, it temporarily stores assets included with that page, e.g. images, stylesheets, and scripts. This means your browser can quickly reload those things later, instead of having to download them again every time you change page. However, it also means that once your site's online, any changes you make to those files won't immediately appear for anyone who recently visited your site. It takes a little while for the cached files to be overwritten with new copies.

If you want changes to appear (almost) immediately then you need to use a cache-buster. One common way is to end the updated file's URL with a query containing a timestamp of when the file was edited, or just random unique text, e.g. `src="main.js"` becomes `src="main.js?v=2024-08-31"`. This forces browsers to download the latest version, but it needs to be updated on every page you want to use the updated file (which might be every page on your blog). You can either use a multi-file find-and-replace (as offered by many plaintext editors) or do it by hand.

If you want to see changes immediately without using a cache-buster, have your browser do a [hard refresh](https://filecamp.com/support/problem-solving/hard-refresh/) on any page that uses the updated file(s). This only affects that specific browser on that specific computer.

#### How to add a new post

First, create the post file:

1. Copy the **post template** file and rename it with the post's title and the date in YYYY-MM-DD format.
2. Open the file and write your post in HTML.
3. Write your post's name in the `title` and `<h1>` elements.

Then, update the script:

1. Open `main.js` and find `posts`.
2. Copy the latest post's data (it looks like this: `{"title": *, "filename": *, "tags": [*]},`) and paste it again at the top of the array.
3. Write your post's title (this can include HTML), filename (*not* including the `.html`), and, optionally, tags.

Here's what a `posts` array with a few posts might look like:

```js
const posts = [
{
	"title": `All about my OCs and the webcomic I'm making about them`,
	"filename": `2023-06-01-all-about-my-ocs-and-webcomic`,
	"tags": [`comics`, `my art`, `my OCs`, `fantrolls`],
},
{
	"title": `Spit buckets and slaughter: a look back at Homestuck`,
	"filename": `2023-05-17-spit-buckets-and-slaughter-a-look-back-at-homestuck`,
	"tags": [`comics`, `history`, `Homestuck`, `Flash`, `the death of Flash`],
},
{
	"title": `My first post!`
	"filename": `2023-05-06-start-here`,
},
];
```

#### How to change the header messages

Adding, changing, and removing header messages is even easier than adding posts. All messages are stored in `messages` array in `main.js`. To remove a message, delete that line. To change a message, change the text between the quote marks. To add a message, write the message on a new line between quote marks (make sure every line has a comma at the end, after the closing quote mark). Most typical HTML is fine to use in these messages (e.g. links).

To switch messages off, set the `messagesOn` parameter at the start of the file to `false`.

#### How to add a favicon

Your favicon should be a `.ico` file placed in the `resources` folder. You can easily create a `.ico` file from any image using [RealFaviconGenerator](https://realfavicongenerator.net/):

1. Upload your image.
2. Scroll to the bottom and click "Generate your Favicons".
3. Click "Favicon package" to download your icons.
4. Unzip the package and move the `.ico` file inside to your blog's `resources` folder.

If you want, you can go deeper into the various icon types and options the site provides, but a `.ico` file covers most situations.

I recommend also using an SVG favicon. However, this is a bigger technical hurdle, especially if you're not familiar with Scalable Vector Graphics (SVG) code. If you do add an SVG favicon, run it through the [SVGOMG](https://optimize.svgomg.net/) optimiser and try reducing the "Number precision" setting (not all the way, but maybe a notch away from the left end). Generally you want your SVG favicon to be only a few kilobytes big! Here's some other help:

* Use an emoji as your favicon (see "[How To Use an Emoji as a Favicon Easily](https://css-tricks.com/emoji-as-a-favicon/)" from CSS-Tricks).
* Read the [SVG Pocket Guide](https://svgpocketguide.com/) by Joni Trythall et al. to learn how to write simple, compact SVG code.

If you use both file types, your code should look like this:

```html
<link rel="icon" href="/link/to/favicon.ico?v=YYYY-MM-DD" sizes="48x48">
<link rel="icon" href="/link/to/favicon.svg?v=YYYY-MM-DD" type="image/svg+xml" sizes="any">
```

Remember to update the cache-buster (the part reading `?v=YYYY-MM-DD`) to match the date you upload the file! See above for more info about the cache.

(The `type` attribute on the SVG favicon may be unnecessary in modern browsers, but I'm not sure.)

#### Reserved HTML ids

You're unlikely to need custom `id` attributes when using Zonelots, but if you do use them, don't use any of these:

* `skip-link`
* `container`
	* `header`
		* `main-nav`
		* `header-message`
	* `content`
		* `post-date`
		* `post-tags`
		* `latest-posts`
		* `tag-index`
		* `all-posts`
	* `footer`
		* `post-nav`
		* `contact-links`

## Examples

Zonelots is used in/inspired code on the following sites (or their blog sections), that I'm aware of:

* <https://splendide-mendax.com/> ([Bumblebee framework](https://splendide-mendax.com/pages/bumblebee_site_framework.html))
* <https://strflr.neocities.org/blog/>
* <https://fluoneon.neocities.org/>
* <https://strikedoves7.neocities.org/>
* <https://ink-heart.neocities.org/home>
* <https://cervidaze.me/blog/>
* <https://voidlyghost.neocities.org/blog/>
* <https://princesspengy.space/>
* <https://unicodeangel.neocities.org/blog/>
* <https://maphren.neocities.org/?z=/blog/>
* <https://cinnamoelle.neocities.org/blog/>
* <https://sammelsurium.neocities.org/log/>
* <https://henrys-garden-shed.neocities.org/zonelots/>
* <https://snacksgg.me/blog/>
* <https://lapislabel.net/blog/>

...It's a lot more than I expected!
