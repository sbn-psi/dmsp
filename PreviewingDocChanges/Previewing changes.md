# Previewing Changes on PDS-Data-Dictionaries.github.io

## The problem

The PDS-Data-Dictionaries.github.io site is a site similar to a wiki that can be edited by multiple users. However, unlike a wiki, there is no preview function, making it difficult to evaluate edits without having them go live.

## Three Solutions

It is possible to preview your changes either by forking the PDS-Data-Dictionaries.github.io repo, or by cloning the repo to your local machine and using Sphinx. 

There are three ways to preview the changes to your documentation. The first is to fork the PDS-Data-Dictionaries.github.io repo, and publish the fork to a different URL with Github pages. The second way is to use the github action that is built into the PDS-Data-Dictionaries.github.io repo. The third way is to run Sphinx on the repo and convert it into HTML. All three of these methods use the Sphinx processor to generate the HTML, but there are differences in where the source files come from, when the source files are processed, and where the resulting HTML files go.

Sphinx is a python program that will convert Markdown and Restructured Text documents to HTML. While there is an installation that you must perform, it should be possible to install it without administrative privileges.

### Forking the PDS-Data-Dictionaries repo

* Advantages
  * Works anywhere
  * No install necessary
  * You'll probably have to fork to make changes anyway
* Disadvantages
  * Viewing your changes requires a push
  * Your changes are still publicly accessible
  * Takes time to build on the server side
  * Only works with the main branch (unless you reconfigure GitHub pages)


#### Fork the repository

* Go to the [PDS-Data-Dictionaries repo](https://github.com/pds-data-dictionaries/PDS-Data-Dictionaries.github.io)
* Click fork in the upper-right hand corner
* Click your username (or organization, if you have one)
* After a minute, you will be taken to your new repo.

<video width="640" height="480" controls>
  <source src="fork_repo.mp4" type="video/mp4">
</video>

#### Set up github pages

* Go to your repo at `https://github.com/(your user name)/PDS-Data-Dictionaries.github.io`
* Click "Settings"
* Click "Pages"
* Select main from the source
* Click "Save"

<video width="640" height="480" controls>
  <source src="configure_pages.mp4" type="video/mp4">
</video>

#### Navigate to github pages

* After a minute, your preview site will be available at `https://(your user name).github.io/PDS-Data-Dictionaries.github.io/`
* It will show a 404 error until the site is ready. Just try again periodically, until you get the new site.
* Pushing changes will have a similar delay.

<video width="640" height="480" controls>
  <source src="navigate_to_page.mp4" type="video/mp4">
</video>

### Using the PDS-Data-Dictionaries GitHub action

* Advantages
  * Works anywhere
  * No install necessary
  * Branching is simpler than forking
  * Works with any branch
  * Changes are less public than publishing over GitHub pages
* Disadvantages
  * Viewing your changes requires a push
  * Your changes are still publicly accessible
  * Takes time to build on the server side
  * You either need to 
    * configure github tokens (if you're using a fork)
    * have write access to the original repo


### Building the docs locally

* Advantages
  * You can build and preview before pushing the documentaiton
  * Your changes are private until you are ready to publish
  * You know exactly when the build is ready
* Disadvantages
  * Needs python and extra python packages
  * May not work for Windows

#### Installing the files needed to build the docs

* Tools needed:
    * python3
    * pip

* Clone the PDS-Data-Dictionaries repo
    * `git clone https://github.com/pds-data-dictionaries/PDS-Data-Dictionaries.github.io.git`
    * or clone your fork: `git clone git@github.com:(your user name)/PDS-Data-Dictionaries.github.io.git`
    * You can also 
* Go to the PDS-Data-Dictionaries.github.io directory
    * `cd PDS-Data-Dictionaries.github.io`
* Install the build system
    * `pip3 install -r requirements.txt`

* What if I don't have admin?
    * `pip3 install --user -r requirements.txt`

#### Build the docs

* Go to the docs directory
    * `cd docs`
* Build the html    
    * `make clean html`

#### View the docuementation

* Open the files using your file browser
    * Navigate to the docs directory on your local system at `PDS-Data-Dictionaries.github.io/docs/build/html`
    * Open `index.html`
* Mac: use the open command:
    * `open build/html/index.html`
    * This might work on linux, but it might be something besides open, like `xdg-open`