+++
date = '2026-10-02T16:32:49+03:00'
draft = false
title = 'Assignment 1'
+++
## Overview

This week I built this website to document my digital fabrication work. I used Hugo to generate the site, GitHub to store it, and GitHub Pages to publish it.

## 1. Git

I installed Git with Homebrew and checked it worked:

    brew install git
    git version

To connect to GitHub from the terminal, I used the GitHub CLI instead of an SSH key:

    brew install gh
    gh auth login

## 2. Creating the site with Hugo

I installed Hugo and created a new site:

    brew install hugo
    hugo new site mywebsite
    cd mywebsite
    git init

I added the hugo-theme-nix theme as a git submodule and set `theme = "hugo-theme-nix"` in `hugo.toml`. 

## 3. Publishing on GitHub

I connected my local folder to my GitHub repository and pushed it:

    git remote add origin https://github.com/fahirataalaca/Digital-Fabrication.git
    git add .
    git commit -m "First version of site"
    git push -u origin main

Then in the repo settings I went to Pages, chose GitHub Actions as the source, and used the Hugo workflow. Now every time I push, the site builds and updates automatically.

## 4. Writing content

I write my pages in Obsidian, using the `content` folder of the site as the vault. After that, the workflow is:

1. Write or edit the page in Obsidian
2. Check it locally with `hugo server`
3. `git add .`, `git commit -m "..."`, `git push`

## What I'd do differently

I'd pick a more actively maintained theme. Nix is old, and my time went into fixing its config and broken links.
