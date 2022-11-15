# Editing this Website

First, install `hugo` by downloading the hugo-extended binary for your operating system, from here <https://gohugo.io/installation/>

## To edit an existing semester portfolio

1. Clone this repo
2. Edit the appropriate markdown file in content/students
3. Run `hugo server -D -t etch` to preview the site locally
4. Commit and push to GitHub, where GitHub Actions will rebuild the site

## To add a new semester portfolio

1. Clone this repo
2. Run `hugo new students/YYYY-SEMESTER.md` (replace YYYY and SEMESTER, of course)
3. Edit the markdown file in content/students (look at other files in that folder for the format)
4. Run `hugo server -D -t etch` to preview the site locally
5. Commit and push to GitHub, where GitHub Actions will rebuild the site

## Some notes about getting Hugo to work with GitHub Pages

* This is an old repo with `master` as the name of the main branch. The GitHub Actions workflow had to be adjusted in a couple places to match that. 
* The GitHub Actions workflow deploys to the `gh-pages` branch, so the Pages section of the repo settings had to be changed to serve from that branch.
* Although the `config.toml` file specifies that the build directory is `/docs`, that's just referring to local Hugo builds. The action does not look at that, so the Pages settings should be set to the root directory of the `gh-pages` branch. 
* Jekyll isn't used because part of the action's deploy is to add a `.nojekyll` file.
