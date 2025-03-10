[![Netlify Status](https://api.netlify.com/api/v1/badges/8cf65901-dae4-4826-b32b-17feeebddc86/deploy-status)](https://app.netlify.com/sites/kind-montalcini-bed86a/deploys)


# Creating and updating the docs 
Welcome to the GitHub repository for Volcano's public website. The docs are
hosted at https://volcano.sh.

We use [Hugo](https://gohugo.io/) to format and generate our website, and
[Netlify](https://www.netlify.com/) to manage the deployment of the site. Hugo
is an open-source static site generator that provides us with templates, content
organisation in a standard directory structure, and a website generation engine.
You write the pages in Markdown, and Hugo wraps them up into a website.

* Please see [How to contributing](https://github.com/volcano-sh/volcano/blob/master/contribute.md) for instruct ions on how to contribute, if you are not familiar with the
  GitHub workflow

## Quickstart

Here's a quick guide to updating the docs. It assumes you're familiar with the
GitHub workflow and you're happy to use the automated preview of your doc
updates:

1. Fork the repo on GitHub.
1. Make your changes and send a pull request (PR).
1. If you're not yet ready for a review, add a comment to the PR saying it's a
  work in progress or add `[WIP]` in your PRs title. You can also add `/hold` in a comment to mark the PR as not
  ready for merge. (**Don't** add the Hugo declarative "draft = true" to the
  page front matter, because that will prevent the auto-deployment of the
  content preview described in the next point.)
1. Wait for the automated PR workflow to do some checks. When it's ready,
  you should see a comment like this: **deploy/netlify — Deploy preview ready!**
1. Click **Details** to the right of "Deploy preview ready" to see a preview
  of your updates.
1. Continue updating your doc until you're happy with it.
1. When you're ready for a review, add a comment to the PR and assign a
  reviewer/approver. 

## Previewing your changes on a local website server

If you'd like to preview your doc updates as you work, you can install Hugo
and run a local server. This section shows you how.

### Install Hugo

See the [Hugo installation guide][hugo-install]. Here are some examples:

#### Mac OS X:

```
brew install hugo
```

#### Debian:

1. Download the Debian package from the [Hugo website][hugo-install].
   Make sure to install the Hugo version specified by the `HUGO_VERSION` environment variable in the [`netlify.toml`](netlify.toml#L6) file.
   For example, [hugo_0.57.2_Linux-64bit.deb][hugo_0.57.2_Linux-64bit.deb].
1. Install the package using `dpkg`:

    ```
    sudo dpkg -i hugo_0.57.2_Linux-64bit.deb
    ```

1. Verify your installation:

    ```
    hugo version
    ```

### Run a local website server

Follow the usual GitHub workflow to fork the repo on GitHub and clone it to your
local machine, then use your local repo as input to your Hugo web server:

1. Ensure you are in your target branch:

    ```
    git branch
    ```

1. Start your website server. Make sure you run this command from the
   `/website/` directory, so that Hugo can find the config files it needs:

    ```
    hugo server -D
    ```

1. Your website is at [http://localhost:1313/](http://localhost:1313/).

1. Continue with the usual GitHub workflow to edit files, commit them, push the
  changes up to your fork, and create a pull request. (See the GitHub workflow)

1. While making the changes, you can preview them on your local version of the
  website at [http://localhost:1313/](http://localhost:1313/). Note that if you
  have more than one local git branch, when you switch between git branches the
  local website reflects the files in the current branch.

Useful Hugo docs:
- [Hugo installation guide](https://gohugo.io/getting-started/installing/)
- [Hugo basic usage](https://gohugo.io/getting-started/usage/)
- [Hugo site directory structure](https://gohugo.io/getting-started/directory-structure/)
- [hugo server reference](https://gohugo.io/commands/hugo_server/)
- [hugo new reference](https://gohugo.io/commands/hugo_new/)

[hugo-install]: https://gohugo.io/getting-started/installing/
[hugo_0.57.2_Linux-64bit.deb]: https://github.com/gohugoio/hugo/releases/download/v0.57.2/hugo_0.57.2_Linux-64bit.deb
