### Stage 1. Draft written in [Obsidian](https://obsidian.md/) [MD]

- Created all text (except subtopics), bi-directional links, and Obsidian-only folder structure

#### Tools

- Obsidian: content creation and bi-directional links
	- Specific folder structure to draft site's and differentiate between content that has been added to site and which hasn't (still in progress).
- Markdown language: content creation (headers, quotes, linking, etc)
- GitHub + GitHub Desktop: [Public GitHub repo](https://github.com/MarySeph/MarySeph.github.io/tree/md-vault) for **version control** and **cloud saving**
    - Branches: "main," "gh-pages," and "md-vault"
    - Commit draft to "md-vault"
    - Tip: Add "Cards/Files" to .gitignore file (through GitHub Desktop) to prevent issues during commits.
- Basic knowledge of Git: manipulate GitHub Desktop (creating repo, making commits, pushing, merging branches)

### Stage 2. Online version created with [Stroll](https://giffmex.org/stroll/stroll.html) [HTML]

- Markdown files imported and edited to a modified version of TiddlyWiki.
    - Ex. OBD transclusion syntax has to be replaced with its [TiddlyWiki counterpart](https://tiddlywiki.com/static/Transclusion%2520Basic%2520Usage.html), and everything above the beginning of the body of the text is removed (eg. metadata, navigation text, and title). 
- Tags are the main element that give the site its structure found in the sidebar and function as a navigation tool because of their dropdown functionality.
    - Click on the pencil symbol at the top right of any draft. Syntax `{{Tiddler Name}}` displays that tiddler.
- Some color-coded tags:
	- Status (green): Evergreen, Budding
	- Type (red): Essay, Log, Reflection, Research
	- (orange): Effort
	- Others: Needs Attention (yellow), topics (pink)
- Created text to subtopic tiddlers in software.
	- Added<<list-links "[tag[<tag name here>]]">> to display all tiddlers under dropdown.

#### Tools
- Stroll + TiddlyWiki(TW) (.html): software you're using right now.
- GitHub Desktop: Private GitHub Repo for automatic cloud saving local working copy of HTML file (aka the Tiddlywiki project). See ("GitHub Saver" from Control Panel).
    - Requires key, target repo, target branch, and name file (opt.)
- [Soren Bjornstad's Mosaic Muse](https://zettelkasten.sorenbjornstad.com/#PublicHomepage:PublicHomepage) has been and *will continue to be* an amazing inspiration for the site's design.

#### Important Plugins & Themes

- [Stroll](https://giffmex.org/stroll/stroll.html): Buffs up TW with bi-directional linking and a couple other things.
- [Relink](https://flibbles.github.io/tw5-relink/): Updates name of a tiddler in all tiddlers it's mentioned.
- [Markdown](https://tiddlywiki.com/plugins/tiddlywiki/markdown/): Allows extensive use of MD, removing need to change a lot of syntax from the OG file format (eg. MD).
- ["Notebook" theme](https://saqimtiaz.github.io/sq-tw/notebook.html): improves visibility of content and is mobile-friendly.
    - Downside is that two-river feature from Stroll doesn't work very well :(.



### Stage 3. Deployed through [GithubPages](https://pages.github.com/) (gh-pages branch) [HTML]

- Upload a local copy renamed "index.html" to public repo "gh-pages" branch.

#### Tools

- [GithubPages](https://pages.github.com/): deployment and troubleshooting with website.
- GitHub Desktop: Public [GitHub repo](https://github.com/MarySeph/MarySeph.github.io/tree/gh-pages) (same as Stage 1 but different branch) for uploading exported index.html to "gh-pages" and deployment.

### Next Steps

---

This is a summary of...

Read through my web development logs in [Cohost](https://cohost.org/MarySeph) or {{Cohost Updates}} for a deeper-look.