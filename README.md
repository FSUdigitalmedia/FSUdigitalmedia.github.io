# Editing this Website

First, install `hugo` by downloading the hugo-extended binary for your operating system, from here <https://gohugo.io/installation/>

The basic process of changing this site is:

1. Clone this repo (or your fork, as described in the next section) to your computer
2. Make changes to the Markdown files
3. Get Hugo to show you a local preview of what the website will look like with your changes
4. Push your changes back to GitHub (or create a Pull Request)

## Clone or Fork this Repo

If you are a member of the FSUdigitalmedia org on GitHub, you can simply clone this repo to get started.

If you aren't, and still want to contribute changes, then you'll go through a different process:

1) Fork the repo (which creates a copy of this repo in your GitHub account)
2) Clone that repo to your computer
3) Make your changes and preview them with Hugo, as described below
4) Commit and push your changes to your fork repo
4) Create a Pull Request on GitHub, so someone from the FSUdigitalmedia org can merge your updated fork back into this repo.

## To edit an existing semester portfolio

Assuming you've cloned this repo (or your fork) to your computer, as described above:

1. Edit the appropriate markdown file in content/portfolio
2. Run `hugo server -D -t etch` to preview the site locally
3. Commit and push to GitHub, where GitHub Actions will rebuild the site
4. Create a Pull Request, if necessary

## To add a new semester portfolio

Again, assuming you've cloned this repo (or your fork) to your computer, as described above:

1. Run `hugo new portfolio/YYYY-SEMESTER-COURSE.md` (replace YYYY and SEMESTER, of course, and use a short abbreviation for COURSE)
2. Edit the markdown file in content/portfolio (look at other files in that folder for the format)
3. Run `hugo server -D -t etch` to preview the site locally
4. Commit and push to GitHub, where GitHub Actions will rebuild the site
5. Create a Pull Request, if necessary

## Some notes about editing the site

* If you're never used Hugo, note that editing the site happens pretty much exclusively via the Markdown files inside the `content` folder (and also via the `config.toml` file). Don't bother editing any html files.
* Always preview the site locally before committing and pushing to GitHub. If you run the hugo server command shown above, the site will automatically be regenerated and refreshed in your browser whenever you save any file. Neat.

## Some notes about getting Hugo to work with GitHub Pages

* This is an old repo with `master` as the name of the main branch. The GitHub Actions workflow had to be adjusted in a couple places to match that. 
* The GitHub Actions workflow deploys to the `gh-pages` branch, so the GitHub Pages section of the repo settings had to be changed to serve the HTML pages from that branch.
* Although the `config.toml` file specifies that the build directory is `/docs`, that's just referring to local Hugo builds. The action does not look at that, so the Pages settings should be set to the root directory of the `gh-pages` branch. 
* Jekyll isn't involved at all, because part of the action's deploy is to add a `.nojekyll` file.
