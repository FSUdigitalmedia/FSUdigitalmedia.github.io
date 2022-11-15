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
