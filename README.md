# MuseumXTD website

The MuseumXTD website uses simple text files in .markdown format to store its content. It needs Obsidian on a computer to edit the content and GitHub to host the pages. 

<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->

  - [Getting started](#getting-started)
    - [Install the Github Desktop app](#install-the-github-desktop-app)
      - [Signing-in](#signing-in)
      - [Getting the content onto your computer](#getting-the-content-onto-your-computer)
    - [Install Obsidian](#install-obsidian)
      - [Making changes](#making-changes)
    - [Publishing to the website](#publishing-to-the-website)
  - [Alternative setup with Obsidian Git](#alternative-setup-with-obsidian-git)
    - [Install git for windows](#install-git-for-windows)
    - [Clone the museumXTD project](#clone-the-museumxtd-project)
    - [Install Obsidian](#install-obsidian-1)
    - [Configuring Obsidian to automatically sync with GitHub to pull latest changes and to push new content](#configuring-obsidian-to-automatically-sync-with-github-to-pull-latest-changes-and-to-push-new-content)
      - [Some basic commands](#some-basic-commands)
  - [Adding new MarkDown files](#adding-new-markdown-files)
    - [New images](#new-images)
- [Without Obsidian](#without-obsidian)
  - [Running locally](#running-locally)
  - [Updating changes manually to the live hosting server on GitHub pages](#updating-changes-manually-to-the-live-hosting-server-on-github-pages)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->
## Getting started

**The recommanded editing process is as follows:**

- Pull the latest version of the website with the GitHub Desktop app 
- Edit the files in the Obsidian app
- Push the changes with the GitHub Desktop app

You will need a GitHub account and permission to access the repository. 


### Install the Github Desktop app  

First you will need to clone the repository (the website content) to your personal computer. Go to the [GitHub Desktop page](https://desktop.github.com), download and install the app on your computer.

#### Signing-in

Open GitHub desktop and sign-in with your GitHub account.

Windows: menu File > Options. In the options window, click Accounts and follow the steps to sign in.

MacOS: menu GitHub Desktop > Preferences. In the preference window, click Accounts and follow the steps to sign in.

#### Getting the content onto your computer
1. Go to the [MuseumXTD repository page](https://github.com/MediaComem/museumXTD/)
1. Click the Clone button 
1. Copy the URL
1. Open the GitHub Desktop app
1. Go to menu File > Clone repository. Click on the URL tab and paste in the field named "Repository URL or GitHub username and repository".

You will see a new folder called **museumXTD** inside of your Documents > GitHub folder which contains all the project files.

![screenshot of github desktop](/images/read-me-images/screenshot-repository-page.png)

### Install Obsidian
If you wish to view the projects Markdown files and make changes or add new content you can do this via Obsidian. There are instructions on the [Obsidian-website](https://obsidian.md/) on how to install this tool. Once done you can select **Open folder as vault** and select the recently cloned project **museumXTD** which was created in your documents folder in the steps above.

#### Making changes
Before making changes make sure you have the latest version of the content.
1. In GitHub Desktop check that the current branch is `main`
1. Click "Fetch Origin"

![screenshot of github desktop](/images/read-me-images/screenshot-github_desktop-branch.png)

In Obsidian edit the content in the Notes folder. Only files saved to the Notes folder will be published on the website. 

### Publishing to the website
Open GitHub Desktop 
1. Write a summary about your changes
1. Click the *Commit* button

![screenshot of github desktop](/images/read-me-images/screenshot-github_desktop.png)

## Alternative setup with Obsidian Git

### Install git for windows
First we need to clone the repository to our local windows machine from GitHub. We do that by installing 'git'. Please go to the [git-for-windows](https://gitforwindows.org/) website and follow the simple instructions to install. You will need to have your GitHub account added to the repository by the admin to be able to pust new commits. 
1. Set your git email address and username
    ```
    git config --global user.email "MY_NAME@example.com"
    git config --global user.name "YOUR USER NAME"
    ```
### Clone the museumXTD project
1. Open a terminal by pressing the *windows key* and start typing *terminal*. Select the **terminal** app from the programs list. The Terminal will open under the default location: C:/Users/XXXXX
2. Change directory to where you want to store the project. For example under your main documents folder and clone the project. Example below:
    ```
    cd .\Documents\
    git clone https://github.com/MediaComem/museumXTD.git
    ```
  You will see a new folder called **museumXTD** inside of your Documents folder which contains all the project files.
### Install Obsidian
If you wish to view the projects Markdown files and make changes or add new content you can do this via Obsidian. There are instructions on the [Obsidian-website](https://obsidian.md/) on how to install this tool. Once done you can select **Open folder as vault** and select the recently cloned project **museumXTD** which was created in your documents folder in the steps above.
### Configuring Obsidian to automatically sync with GitHub to pull latest changes and to push new content
Open the settings tab on Obsidian and select **Community plugins**. Next turn off safe mode and search for and install the plugin **Obsidian Git**. As you cloned the museumXTD project from GitHub, Obsidian Git will automatically see it as a git project giving you access to its native commands to pull or push changes. Please read the guide material to understand the different settings available to you.
#### Some basic commands
Currently one of the menu items on Obsidian is **Open command palette**. Here you can enter the Obsidian Git commands to save changes and upload them to the GitHub repository.
- **Pull** This command is automatically triggered when you open the project with Obsidian. However it is good practice to pull from the repository just before you commit any changes in case there are some other recent changes which you are missing.
- **List changed files** Before you commit your changes you can view a list of all the files that have been changed to verify and not to push unwanted changes by mistake.
- **Open source control view** If you want to inspect each file change line by line you can use this command to compare before (red) and after (green).
- **commit all changes** This command will add your changes to the git staging area and then perform a commit. There is a standard default message attached to the commit. Usually something like *vault backup: YYYY-MM-DD hh:mm:ss* However **I advise to change this** to include your name so your team can track in the logs history who is doing what changes. Under `Obsidian settings, Community plugins, Obsidian Git, options`, here there is the field *Commit message on manual backup/commit*. You can enter your custom message here that will appear on every commit thereafter.
- **Push** Finally once you made your commit you can push your changes to the GitHub repository. This should trigger a build to publish the new version to GitHub-pages. Note it can take a few moments for the changes to take effect on the live server and you may need to clear cache on your browser if the page is already loaded. You can also view the website in *incognito mode* chrome or *InPrivate window* Edge so not to use any old cookies or cache.

## Adding new MarkDown files
- **title** This property is referenced in the ***layouts/base.njk*** HTML to use as the title to the browser tab. If not set it has the default value as *MuseumXTD* 
- **layout** We add this to have your MD file contained in some HTML/CSS referenced in a njk file. For this project we have the standard HTML/CSS applied with layouts/post.njk
- **tags** For Obsidian you can add this meta data for finding relative documents.
- If you want to add other properties like **date** please add as a comment with the `#` symbol before it to avoid breaking the build process with invalid formats or data. This has been included in the template.md file as well as below for reference.

Below is an example of the standard properties to add to your new MD file. post.njk will import the HTML from `base.njk` which imports the `main.css` styles to apply to your page.
```
---
title: MuseumXTD
layout: layouts/post.njk
date: #2022-06-23
tags: liens forum francais
---
```
There is a **template.md** file on the root of the project which you can copy for creating new markdown Files. If you wish to apply another layout to your MD file you can reference it's file name instead. Be sure to save your new layout file in the right folder *layouts* and have the correct syntax. Your MD file content will be rendered where you have added the following line `{{ content | safe }}` on your new .njk file

### New images
All images are to be stored in the root **images** folder. When referencing any image on a MD file please follow this example `/images/nameFile.png`
# Without Obsidian
## Running locally
- **install Node** The official [Node-website](https://nodejs.org/en/download/) give instructions on how to install node.

You can run the project locally by first downloading the required packages `npm ci` from the package-lock.json and then running `npm run start`. This will build the project files and store them on the docs folder. Next Eleventy will serve this docs folder on your local host to view on your browser `Local: http://localhost:8080`

## Updating changes manually to the live hosting server on GitHub pages
When you have committed your local changes with `git add` and `git commit -m "enter message here"` and pushed to the GitHub branch **main** `git push origin main`, which has the **eleventy_build.yml** file, this will trigger a build of the project on GitHub and push the created files to the **docs** folder. Next this folder, which will contain the Eleventy build, is pushed to the **gh-pages** branch. This branch will automatically update on the live host in a few moments.
