+++
date = '2026-10-02T16:32:49+03:00'
draft = false
title = 'Assignment 1'
+++
## Overview

This week I built this website to document my digital fabrication work. I used Hugo to generate the site, GitHub to store it, GitHub Pages to publish it, and Obsidian to write the pages. I followed a tutorial written for GitLab and the Blowfish theme, but adapted it to GitHub and the Nix theme, so some steps are different.

## 1. Git

I installed Git with Homebrew and checked it worked:

    brew install git
    git version

The tutorial uses an SSH key to connect to GitLab. Since I use GitHub, I logged in with the GitHub CLI instead, which does the same job:

    brew install gh
    gh auth login

## 2. Creating the site with Hugo

I installed Hugo and created a new site:

    brew install hugo
    hugo new site mywebsite
    cd mywebsite
    git init

Then I added the hugo-theme-nix theme as a git submodule and set `theme = "hugo-theme-nix"` in `hugo.toml`:

    git submodule add https://github.com/LordMathis/hugo-theme-nix.git themes/hugo-theme-nix

To preview the site locally I ran `hugo server` and opened `http://localhost:1313/`.

### Problems

- **404 page:** at first the preview showed a 404. I was running `hugo server` from the wrong folder, and the theme setting was missing from the config.
- **Empty homepage:** after fixing that, the page was blank. This theme builds its homepage from settings in the config file, so I copied them from the theme's example site and replaced them with my own info.

## 3. Publishing on GitHub

I connected my local folder to my GitHub repository and pushed it:

    git remote add origin https://github.com/fahirataalaca/Digital-Fabrication.git
    git add .
    git commit -m "First version of site"
    git push -u origin main

### Problems

- **Push rejected:** the repo on GitHub already had a README, so its history didn't match mine. I fixed it by merging the two:

      git pull origin main --allow-unrelated-histories

- **Theme added wrong:** the theme had been copied in as a separate repository inside mine instead of a submodule, so GitHub couldn't build it. I removed it and added it again with `git submodule add`.
- **Unwanted files:** I added `public/` (the generated site) and `.DS_Store` (a macOS system file) to `.gitignore` so they don't get uploaded.

### GitHub Pages

In the repo settings I went to **Pages** and chose **GitHub Actions** as the source. Hugo wasn't in the suggested workflows, so I clicked **browse all workflows**, searched for Hugo, and committed its workflow file. Then I pulled that file back to my laptop:

    git pull origin main --rebase

Now every time I push, the site builds automatically, and a green check in the **Actions** tab means it's live at https://fahirataalaca.github.io/Digital-Fabrication/

## 4. Cleaning up the config

The example config came with leftovers that didn't work on my site:

- A **Disqus** comments box that showed an error. I deleted the Disqus line.
- The header said "Ata@gohugo.io". I changed `HeaderHostname` to "ideaLab".
- The **about** and **post** menu links led to pages that don't exist. I removed "about" and replaced "post" with an "assignments" link to `/posts`.
- I added my GitHub username so the GitHub icon links to my account.

## 5. Writing content

I created this page with:

    hugo new content posts/assignment-1.md

New pages start with `draft = true`, which hides them, so I changed it to `draft = false` before publishing.

My teacher asked us to write documentation in Obsidian, a Markdown note-taking app. I installed it and opened the site's `content` folder as the vault, so every note I write there is already a page on the site:

    brew install --cask obsidian

My workflow now is:

1. Write or edit the page in Obsidian
2. Check it locally with `hugo server`
3. Publish it:

       git add .
       git commit -m "..."
       git push

## What I'd do differently

I'd pick a more actively maintained theme. Nix is old, and most of my time went into fixing its config and broken links instead of working on content.
