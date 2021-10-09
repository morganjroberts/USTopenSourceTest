# Testing for future open source UST docs

Visit the [BUG website](https://bug.medphys.ucl.ac.uk/) to find out more.

## Useful links
* [MkDocs User Guide](https://www.mkdocs.org/user-guide/)
* [Markdown Syntax Guide](https://www.markdownguide.org/basic-syntax/)

## Strategy

* Create empty remote repo on github website
* Create empty local repo directory on laptop by typing `mkdocs new <project_dir_name>`
* Change directories `cd project_dir_name`
* Open local repo directory in a VScode terminal (terminal should always stay at the root)
* Clone remote repo to transform local repo into a git repo by copying the link and typing `git clone <link>`
* MkDocs will create a site directory that should not be tracked. Add `site/` to .gitignore
* Add documentation using the following file structure:

```
repo_name/        # Root directory (open terminal here)
    mkdocs.yml    # The configuration file.
    docs/
        index.md  # The documentation homepage.
        about.md
        license.md
        img/
            screenshot.png   
```     

* You can then reference images using a relative path e.g. `![screenshot](img/screenshot.png)`
* Embed youtube videos by directly copying the HTML embed code into the markdown file.
* Preview the documentation locally using `mkdocs serve`, stop this using `Ctrl + C`
* MkDocs references what is on the remote repo, so it needs to be up to date before building and deploying the documentation:
    * Add files for tracking `git add .`
    * Commit changes `git commit -m "write_a_meaningful_message"`
    * Push local changes to remote repo `git push origin main`
    * Check success using `git status`
* Now simultaneously build and deploy the documentation using `mkdocs gh-deploy`

