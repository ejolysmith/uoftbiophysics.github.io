# UofT Biophysics Blog

Welcome! Below is a detailed summary of how to contribute to the website.

This blog is built on the site structure of [al-folio](https://github.com/alshedivat/al-folio), the details of which you can find below. The creators of this blog did not fork it directly from the source, as the repository for the website existed under another template previously. For the entrepreneurial minds, there are many more webpages you can make (some examples of which are under `_oldpages`. They need only to be edited and moved to the `_pages` folder. Good luck!

## Submitting and reviewing articles

**Join the uoftbiophysics GitHub organization**
1. Make a [GitHub](https://github.com/) account and sign in.
2. Send your GitHub username to Matt or Jeremy to be added to [our GitHub organization](https://github.com/uoftbiophysics).

**Fork the website repo**
1. Go to the [website repository](https://github.com/uoftbiophysics/uoftbiophysics.github.io).
2. In the top right, click "Fork". It should now exist at `https://github.com/YOUR_USERNAME/uoftbiophysics.github.io`.

**Clone the forked copy, make your changes, commit and push them**
1. Install Git locally. You can do everything from terminal or command line, or you can install a git GUI (e.g. SourceTree, GitKraken).
2. Clone the forked repo to your computer.

**Update the code**

1. Make changes to the site files. For posting a blog post, all you need to do is write a new post under `/_posts/`. You can find a template and examples of previous blog posts there. Please copy the file `_ZZZZ-YY-XX-template.md` and rename it. *For the adventurous, you can find other templates under `/_templateposts/`.*
2. Commit then push those changes.

**Create a Pull Request**
1. Go to the [original website repo](https://github.com/uoftbiophysics/uoftbiophysics.github.io).
2. Click "Pull requests" (third tab at the top).
3. Click "New Pull Request".
4. Selection: pull your forked copy and its changes into the original copy.
5. Details: fill out the topic/description, add any reviewers or assignees, and submit.

**Syncing a forked repository**

If you've already forked the repo and cloned it a while ago, the upstream repository code may have changed.
It should be synced before you add more code.
There are [two approaches to do this](https://docs.github.com/en/github/collaborating-with-pull-requests/working-with-forks/syncing-a-fork):

*Web UI*
- Navigate to your forked repo at `https://github.com/YOUR_USERNAME/uoftbiophysics.github.io`.
- Click "Fetch upstream" (below green Code button). Select "Fetch and merge".
- Locally, use `git pull` to update your copy of the fork.

*Command line*
- Configure upstream remote (if you haven't yet): `git remote add upstream https://github.com/uoftbiophysics/uoftbiophysics.github.git`
- Verify it was added: `git remote -v`
- To sync changes, do:
	- `git fetch upstream`
	- `git checkout main`
	- `git merge upstream/main`
- This syncs your local changes. To update your fork on Github you need to `push` any changes.

## Locally viewing the website (and your changes to it) ###

### Windows ###

- [GitHub documentation](https://docs.github.com/en/pages/setting-up-a-github-pages-site-with-jekyll/testing-your-github-pages-site-locally-with-jekyll)
- [Extra documentation](https://idratherbewriting.com/documentation-theme-jekyll/mydoc_install_jekyll_on_windows.html)

*Prerequisites (details in the links above)*
1. [Install Ruby](https://rubyinstaller.org/downloads/) (under WITH DEVKIT, select option to add to PATH).
2. In command line: `gem install bundler`
3. In command line: `gem install jekyll`

*Viewing the site*
1. Open terminal or command line and change directory to the root of the cloned website repository.
2. `bundle install`
3. `bundle exec jekyll serve`
4. Navigate to http://localhost:4000/ and see if it worked.

*Troubleshooting:*
1. A gem file is needed, but should already be on git. In case it isn't, run `> bundle init` to make one.
2. On windows three lines should be added to the end of the file:
- gem 'wdm'
- gem 'jekyll'
- gem "webrick", "~> 1.7"
3. See if `bundle exec jekyll serve` works now.

### Linux ###

*Prerequisites (details in the links above)*

You only need to do this once. Either
1. Install all dependencies by running the script `linux-setup.sh`; or
2. [Follow this guide](https://jekyllrb.com/docs/installation/ubuntu/).

*Viewing the site*

Run the command

```bash
$ jekyll serve
```
and either navigate to [http://localhost:4000/](http://localhost:4000/) or Ctrl+click the link in terminal for it to open automatically in browser.

*Troubleshooting*
1. If the following code appears

```bash
FATAL: Listen error: unable to monitor directories for changes.
        Visit https://github.com/guard/listen/blob/master/README.md#increasing-the-amount-of-inotify-watchers for info on how to fix this.
```
then it is likely your server didn't close properly in an earlier session. You can always increase the number of inotify-watchers by running

```bash
$ echo fs.inotify.max_user_watches=524288 | sudo tee -a /etc/sysctl.conf && sudo sysctl -p
```

Below is the README for al-folio

# al-folio

[![deploy](https://github.com/alshedivat/al-folio/actions/workflows/deploy.yml/badge.svg)](https://github.com/alshedivat/al-folio/actions/workflows/deploy.yml)
[![demo](https://img.shields.io/badge/theme-demo-brightgreen.svg)](https://alshedivat.github.io/al-folio/)
[![GitHub contributors](https://img.shields.io/github/contributors/alshedivat/al-folio.svg)](https://github.com/alshedivat/al-folio/graphs/contributors/)
[![GitHub release](https://img.shields.io/github/v/release/alshedivat/al-folio)](https://github.com/alshedivat/al-folio/releases/latest)
[![GitHub license](https://img.shields.io/github/license/alshedivat/al-folio?color=blue)](https://github.com/alshedivat/al-folio/blob/master/LICENSE)
[![GitHub stars](https://img.shields.io/github/stars/alshedivat/al-folio)](https://github.com/alshedivat/al-folio)
[![GitHub forks](https://img.shields.io/github/forks/alshedivat/al-folio)](https://github.com/alshedivat/al-folio/fork)
[![support](https://img.shields.io/badge/support-Ko--fi-yellow.svg)](https://ko-fi.com/alshedivat)

A simple, clean, and responsive [Jekyll](https://jekyllrb.com/) theme for academics.
If you like the theme, give it a star!

[![Preview](https://raw.githubusercontent.com/alshedivat/al-folio/master/assets/img/al-folio-preview.png)](https://alshedivat.github.io/al-folio/)


## Best practices

[![Google PageSpeeg](https://raw.githubusercontent.com/alshedivat/al-folio/master/assets/img/pagespeed.svg)](https://developers.google.com/speed/pagespeed/insights/?url=https%3A%2F%2Falshedivat.github.io%2Fal-folio%2F&tab=desktop)


## Getting started

For more about how to use Jekyll, check out [this tutorial](https://www.taniarascia.com/make-a-static-website-with-jekyll/).
Why Jekyll? Read [Andrej Karpathy's blog post](https://karpathy.github.io/2014/07/01/switching-to-jekyll/)!


### Installation

#### Local setup

Assuming you have [Ruby](https://www.ruby-lang.org/en/downloads/) and [Bundler](https://bundler.io/) installed on your system (*hint: for ease of managing ruby gems, consider using [rbenv](https://github.com/rbenv/rbenv)*), first [fork](https://guides.github.com/activities/forking/) the theme from `github.com:alshedivat/al-folio` to `github.com:<your-username>/<your-repo-name>` and do the following:

```bash
$ git clone git@github.com:<your-username>/<your-repo-name>.git
$ cd <your-repo-name>
$ bundle install
$ bundle exec jekyll serve
```

Now, feel free to customize the theme however you like (don't forget to change the name!).
After you are done, **commit** your final changes.

#### Deployment

Deploying your website to [GitHub Pages](https://pages.github.com/) is the most popular option.
Starting version [v0.3.5](https://github.com/alshedivat/al-folio/releases/tag/v0.3.5), **al-folio** will automatically re-deploy your webpage each time you push new changes to your repository! :sparkles:

**For personal and organization webpages:**
1. Rename your repository to `<your-github-username>.github.io` or `<your-github-orgname>.github.io`.
2. In `_config.yml`, set `url` to `https://<your-github-username>.github.io` and leave `baseurl` empty.
3. Set up automatic deployment of your webpage (see instructions below).
4. Make changes, commit, and push!
5. After deployment, the webpage will become available at `<your-github-username>.github.io`.

**For project pages:**
1. In `_config.yml`, set `url` to `https://<your-github-username>.github.io` and `baseurl` to `/<your-repository-name>/`.
2. Set up automatic deployment of your webpage (see instructions below).
3. Make changes, commit, and push!
4. After deployment, the webpage will become available at `<your-github-username>.github.io/<your-repository-name>/`.

**To enable automatic deployment:**
1. Click on **Actions** tab and **Enable GitHub Actions**; do not worry about creating any workflows as everything has already been set for you.
2. Make any other changes to your webpage, commit, and push. This will automatically trigger the **Deploy** action.
3. Wait for a few minutes and let the action complete. You can see the progress in the **Actions** tab. If completed successfully, in addition to the `master` branch, your repository should now have a newly built `gh-pages` branch.
4. Finally, in the **Settings** of your repository, in the Pages section, set the branch to `gh-pages` (**NOT** to `master`). For more details, see [Configuring a publishing source for your GitHub Pages site](https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site#choosing-a-publishing-source).


<details><summary>(click to expand) <strong>Manual deployment to GitHub Pages:</strong></summary>

If you need to manually re-deploy your website to GitHub pages, run the deploy script from the root directory of your repository:
```bash
$ ./bin/deploy
```
uses the `master` branch for the source code and deploys the webpage to `gh-pages`.

</details>

<details><summary>(click to expand) <strong>Deployment to another hosting server (non GitHub Pages):</strong></summary>

If you decide to not use GitHub Pages and host your page elsewhere, simply run:
```bash
$ bundle exec jekyll build
```
which will (re-)generate the static webpage in the `_site/` folder.
Then simply copy the contents of the `_site/` foder to your hosting server.

**Note:** Make sure to correctly set the `url` and `baseurl` fields in `_config.yml` before building the webpage. If you are deploying your webpage to `your-domain.com/your-project/`, you must set `url: your-domain.com` and `baseurl: /your-project/`. If you are deploing directly to `your-domain.com`, leave `baseurl` blank.

</details>

<details><summary>(click to expand) <strong>Deployment to a separate repository (advanced users only):</strong></summary>

**Note:** Do not try using this method unless you know what you are doing (make sure you are familiar with [publishing sources](https://help.github.com/en/github/working-with-github-pages/about-github-pages#publishing-sources-for-github-pages-sites)). This approach allows to have the website's source code in one repository and the deployment version in a different repository.

Let's assume that your website's publishing source is a `publishing-source` sub-directory of a git-versioned repository cloned under `$HOME/repo/`.
For a user site this could well be something like `$HOME/<user>.github.io`.

Firstly, from the deployment repo dir, checkout the git branch hosting your publishing source.

Then from the website sources dir (commonly your al-folio fork's clone):
```bash
$ bundle exec jekyll build --destination $HOME/repo/publishing-source
```

This will instruct jekyll to deploy the website under `$HOME/repo/publishing-source`.

**Note:** Jekyll will clean `$HOME/repo/publishing-source` before building!

The quote below is taken directly from the [jekyll configuration docs](https://jekyllrb.com/docs/configuration/options/):

> Destination folders are cleaned on site builds
>
> The contents of `<destination>` are automatically cleaned, by default, when the site is built. Files or folders that are not created by your site will be removed. Some files could be retained by specifying them within the `<keep_files>` configuration directive.
>
> Do not use an important location for `<destination>`; instead, use it as a staging area and copy files from there to your web server.

If `$HOME/repo/publishing-source` contains files that you want jekyll to leave untouched, specify them under `keep_files` in `_config.yml`.
In its default configuration, al-folio will copy the top-level `README.md` to the publishing source. If you want to change this behaviour, add `README.md` under `exclude` in `_config.yml`.

**Note:** Do _not_ run `jekyll clean` on your publishing source repo as this will result in the entire directory getting deleted, irrespective of the content of `keep_files` in `_config.yml`.

</details>


### FAQ

Here are some frequently asked questions. about al-folio
If you have a different question, please ask using [Discussions](https://github.com/alshedivat/al-folio/discussions/categories/q-a).

1. **Q:** After I fork and setup the repo, I get a deployment error.
   Isn't the website supposed to correctly deploy automatically? <br>
   **A:** Yes, if you are using release `v0.3.5` or later, the website will automatically and correctly re-deploy right after your first commit.
   Please make some changes (e.g., change your website info in `_config.yml`), commit, and push.
   Make sure to follow [deployment instructions](https://github.com/alshedivat/al-folio#deployment) in the previous section.
   (Relevant issue: [209](https://github.com/alshedivat/al-folio/issues/209#issuecomment-798849211).)

2. **Q:** I am using a custom domain (e.g., `foo.com`).
   My custom domain becomes blank in the repository settings after each deployment.
   How do I fix that? <br>
   **A:** You need to add `CNAME` file to the `master` or `source` branch of your repository.
   The file should contain your custom domain name.
   (Relevant issue: [130](https://github.com/alshedivat/al-folio/issues/130).)

3. **Q:** My webpage works locally.
    But after deploying, it is not displayed correctly (CSS and JS is not loaded properly).
    How do I fix that? <br>
   **A:** Make sure to correctly specify the `url` and `baseurl` paths in `_config.yml`.
   Set `url` to `https://<your-github-username>.github.io` or to `https://<your.custom.domain>` if you are using a custom domain.
   If you are deploying a personal or organization website, leave `baseurl` blank.
   If you are deploying a project page, set `baseurl: /<your-project-name>/`.

4. **Q:** Atom feed doesn't work. Why?
   <br>
   **A:** Make sure to correctly specify the `url` and `baseurl` paths in `_config.yml`.
  RSS Feed plugin works with these correctly set up fields: `title`, `url`, `description` and `author`.
  Make sure to fill them in an appropriate way and try again.

## Features

### Publications

Your publications page is generated automatically from your BibTex bibliography.
Simply edit `_bibliography/papers.bib`.
You can also add new `*.bib` files and customize the look of your publications however you like by editing `_pages/publications.md`.

<p align="center"><img src="https://raw.githubusercontent.com/alshedivat/al-folio/master/assets/img/publications-screenshot.png" width=800></p>

<details><summary>(click to expand) <strong>Author annotation:</strong></summary>

In publications, the author entry for yourself is identified by string `scholar:last_name` and string array `scholar:first_name` in `_config.yml`:
```
scholar:
  last_name: Einstein
  first_name: [Albert, A.]
```
If the entry matches the last name and one form of the first names, it will be underlined.
Keep meta-information about your co-authors in `_data/coauthors.yml` and Jekyll will insert links to their webpages automatically.
The coauthor data format in `_data/coauthors.yml` is as follows,
```
"Adams":
  - firstname: ["Edwin", "E.", "E. P.", "Edwin Plimpton"]
    url: https://en.wikipedia.org/wiki/Edwin_Plimpton_Adams

"Podolsky":
  - firstname: ["Boris", "B.", "B. Y.", "Boris Yakovlevich"]
    url: https://en.wikipedia.org/wiki/Boris_Podolsky

"Rosen":
  - firstname: ["Nathan", "N."]
    url: https://en.wikipedia.org/wiki/Nathan_Rosen

"Bach":
  - firstname: ["Johann Sebastian", "J. S."]
    url: https://en.wikipedia.org/wiki/Johann_Sebastian_Bach

  - firstname: ["Carl Philipp Emanuel", "C. P. E."]
    url: https://en.wikipedia.org/wiki/Carl_Philipp_Emanuel_Bach
```
If the entry matches one of the combinations of the last names and the first names, it will be highlighted and linked to the url provided.

</details>

<details><summary>(click to expand) <strong>Buttons (through custom bibtex keywords):</strong></summary>

There are several custom bibtex keywords that you can use to affect how the entries are displayed on the webpage:

- `abbr`: Adds an abbreviation to the left of the entry. You can add links to these by creating a venue.yaml-file in the _data folder and adding entries that match.
- `abstract`: Adds an "Abs" button that expands a hidden text field when clicked to show the abstract text
- `arxiv`: Adds a link to the Arxiv website (Note: only add the arxiv identifier here - the link is generated automatically)
- `bibtex_show`: Adds a "Bib" button that expands a hidden text field with the full bibliography entry
- `html`: Inserts a "HTML" button redirecting to the user-specified link
- `pdf`: Adds a "PDF" button redirecting to a specified file (if a full link is not specified, the file will be assumed to be placed in the /assets/pdf/ directory)
- `supp`: Adds a "Supp" button to a specified file (if a full link is not specified, the file will be assumed to be placed in the /assets/pdf/ directory)
- `blog`: Adds a "Blog" button redirecting to the specified link
- `code`: Adds a "Code" button redirecting to the specified link
- `poster`: Adds a "Poster" button redirecting to a specified file (if a full link is not specified, the file will be assumed to be placed in the /assets/pdf/ directory)
- `slides`: Adds a "Slides" button redirecting to a specified file (if a full link is not specified, the file will be assumed to be placed in the /assets/pdf/ directory)
- `website`: Adds a "Website" button redirecting to the specified link

You can implement your own buttons by editing the bib.html file.

</details>

### Collections

This Jekyll theme implements `collections` to let you break up your work into categories.
The theme comes with two default collections: `news` and `projects`.
Items from the `news` collection are automatically displayed on the home page.
Items from the `projects` collection are displayed on a responsive grid on projects page.

<p align="center"><img src="https://raw.githubusercontent.com/alshedivat/al-folio/master/assets/img/projects-screenshot.png" width=700></p>

You can easily create your own collections, apps, short stories, courses, or whatever your creative work is.
To do this, edit the collections in the `_config.yml` file, create a corresponding folder, and create a landing page for your collection, similar to `_pages/projects.md`.

### Layouts

**al-folio** comes with stylish layouts for pages and blog posts.

#### The iconic style of Distill

The theme allows you to create blog posts in the [distill.pub](https://distill.pub/) style:

<p align="center"><a href="https://alshedivat.github.io/al-folio/blog/2018/distill/" target="_blank"><img src="https://raw.githubusercontent.com/alshedivat/al-folio/master/assets/img/distill-screenshot.png" width=700></a></p>

For more details on how to create distill-styled posts using `<d-*>` tags, please refer to [the example](https://alshedivat.github.io/al-folio/blog/2018/distill/).

#### Full support for math & code

**al-folio** supports fast math typesetting through [MathJax](https://www.mathjax.org/) and code syntax highlighting using [GitHub style](https://github.com/jwarby/jekyll-pygments-themes):

<p align="center">
<a href="https://alshedivat.github.io/al-folio/blog/2015/math/" target="_blank"><img src="https://raw.githubusercontent.com/alshedivat/al-folio/master/assets/img/math-screenshot.png" width=400></a>
<a href="https://alshedivat.github.io/al-folio/blog/2015/code/" target="_blank"><img src="https://raw.githubusercontent.com/alshedivat/al-folio/master/assets/img/code-screenshot.png" width=400></a>
</p>

#### Photos

Photo formatting is made simple using [Bootstrap's grid system](https://getbootstrap.com/docs/4.4/layout/grid/).
Easily create beautiful grids within your blog posts and project pages:

<p align="center">
  <a href="https://alshedivat.github.io/al-folio/projects/1_project/">
    <img src="https://raw.githubusercontent.com/alshedivat/al-folio/master/assets/img/photos-screenshot.png" width="75%">
  </a>
</p>


### Other features

#### Theming
Six beautiful theme colors have been selected to choose from.
The default is purple, but you can quickly change it by editing `$theme-color` variable in the `_sass/_themes.scss` file.
Other color variables are listed there as well.

#### Social media previews
**al-folio** supports preview images on social media.
To enable this functionality you will need to set `serve_og_meta` to `true` in your `_config.yml`.
Once you have done so, all your site's pages will include Open Graph data in the HTML head element.

You will then need to configure what image to display in your site's social media previews.
This can be configured on a per-page basis, by setting the `og_image` page variable.
If for an individual page this variable is not set, then the theme will fall back to a site-wide `og_image` variable, configurable in your `_config.yml`.
In both the page-specific and site-wide cases, the `og_image` variable needs to hold the URL for the image you wish to display in social media previews.

#### Atom (RSS-like) Feed
It generates an Atom (RSS-like) feed of your posts, useful for Atom and RSS readers.
The feed is reachable simply by typing after your homepage `/feed.xml`.
E.g. assuming your website mountpoint is the main folder, you can type `yourusername.github.io/feed.xml`

## Contributing

Contributions to al-folio are very welcome!
Before you get started, please take a look at [the guidelines](CONTRIBUTING.md).

If you would like to improve documentation, add your webpage to the list below, or fix a minor inconsistency or bug, please feel free to send a PR directly to `master`.
For more complex issues/bugs or feature requests, please open an issue using the appropriate template.


## License

The theme is available as open source under the terms of the [MIT License](https://github.com/alshedivat/al-folio/blob/master/LICENSE).

Originally, **al-folio** was based on the [\*folio theme](https://github.com/bogoli/-folio) (published by [Lia Bogoev](https://liabogoev.com) and under the MIT license).
Since then, it got a full re-write of the styles and many additional cool features.
