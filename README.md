## Project Status
| Branch | Live Site | Test Status | CICD Status |
| - | - | - | - |
| `main` | [Production Site](https://enigmaglass-docs.github.io/enigmaglass/) | [![Run Tests - CodeQL](https://github.com/enigmaglass-docs/enigmaglass/actions/workflows/codeql.yml/badge.svg?branch=main)](https://github.com/enigmaglass-docs/enigmaglass/actions/workflows/codeql.yml) | [![pages-build-deployment](https://github.com/enigmaglass-docs/enigmaglass/actions/workflows/pages/pages-build-deployment/badge.svg?branch=main)](https://github.com/enigmaglass-docs/enigmaglass/actions/workflows/pages/pages-build-deployment) |
| `development` | [Development Site](https://enigmaglass-docs.github.io/enigmaglass-dev/) | [![Run Tests - CodeQL](https://github.com/enigmaglass-docs/enigmaglass/actions/workflows/codeql.yml/badge.svg?branch=development)](https://github.com/enigmaglass-docs/enigmaglass/actions/workflows/codeql.yml) | [![Development Build and Deploy](https://github.com/enigmaglass-docs/enigmaglass/actions/workflows/deploy-dev.yml/badge.svg?branch=development)](https://github.com/enigmaglass-docs/enigmaglass/actions/workflows/deploy-dev.yml) [![pages-build-deployment](https://github.com/enigmaglass-docs/enigmaglass-dev/actions/workflows/pages/pages-build-deployment/badge.svg?branch=main)](https://github.com/enigmaglass-docs/enigmaglass-dev/actions/workflows/pages/pages-build-deployment)|

## Project Overview
Welcome to the Enigma Glass training resource. This site has been designed to provide a framework that Enigma Glass or other students can continue to build on.

The major factor that informed our design decisions was ease of development and integration. This project has been setup in a way that attempts to make it as easy as possible to contribute to. The site content development work is done mostly in markdown, but the site can be customized with HTML, CSS, and JS. Due to the include / override nature of Ruby on Rails and Gems, the site will run well and look good without anything other than markdown. 

This project deploys to three distinct environments and features automated build and deploy workflows, in addition to automated testing and dependency scanning.

The site is intended to be served by Jekyll; it was built using a gem theme called `just-the-docs`. When the site is built Jekyll parses all of the markdown files in the directory looking for templating tags and markdown. It then outputs the `_site` directory which contains the static HTML / CSS / JS for the site.

When the site is built a search index is created to be used by Lunr.js to support the site's full-text search functionality. The search runs as clientside javascript, but as this is a small static site the search is still lightning fast.

## Development
1. Clone repository to your local machine:

```bash
git clone git@github.com:enigmaglass-docs/enigmaglass.git

cd enigmaglass

git checkout development
```

![clone repo to local](https://github.com/enigmaglass-docs/.github/blob/main/profile//assets/gif/clone-repo-checkout-development.gif)

2. Checkout feature branch and create draft pull request into `development`:

```bash
git checkout -b feature/{YOUR_FEATURE_NAME_HERE}
```

Now you can make you changes to this branch. When you want to save your changes you can commit and push them to the remote server (Github).

```bash
# see your status
git status

# add all changes
git add .

# commit your changes
git commit -m "this is a commit message"

# push your branch to the remote
git push -u origin feature/{YOUR_FEATURE_NAME_HERE}

# NOTE: after you push your local branch to the remote it will track the remote, so you can just run
# git push
```

Once your local branch has been pushed to the remote server on Github, you can create a draft pull request into the `development` branch to review your changes. You can comment here with links to resources or notes for yourself as you work.

![create feature branch and pr](https://github.com/enigmaglass-docs/.github/blob/main/profile/assets/gif/create-feature-branch-and-pr.gif)

3. Test your changes locally:

```bash
# you must have Ruby and Jekyll installed

`bundle install`

`bundle exec jekyll serve --livereload`
```

![test changes locally](https://github.com/enigmaglass-docs/.github/blob/main/profile/assets/gif/test-changes-locally.gif)

4. Once you're happy with your changes locally you can test your changes using the Pheonix deploy by setting your pull request status as `Ready for Review`.

**Note: Draft pull requests into `development` that are marked as `Ready for Review` will automatically be built and deployed with Github Pages using [the Pheonix Build and Deploy workflow](https://github.com/enigmaglass-docs/enigmaglass/actions/workflows/deploy-pr.yml). This workflow can also be run manually on any branch. When the pull request is closed [the Delete Pheonix Deployment workflow](https://github.com/enigmaglass-docs/enigmaglass/actions/workflows/delete-deploy-pr.yml) will delete the short-lived repository that was created to host the Github Pages site.**

![mark pr ready for review](https://github.com/enigmaglass-docs/.github/blob/main/profile/assets/gif/mark-pr-ready-start-pheonix-deploy.gif)

[![Pheonix Build and Deploy](https://github.com/enigmaglass-docs/enigmaglass/actions/workflows/deploy-pr.yml/badge.svg)](https://github.com/enigmaglass-docs/enigmaglass/actions/workflows/deploy-pr.yml)

5. Once the Pheonix deploy has completed, click `View Deployment` to see you site being served by Github Pages:

![view deployment](https://github.com/enigmaglass-docs/.github/blob/main/profile/assets/gif/view-deployment.gif)

6. When you're ready to promote your changes to `development` and your pull request has been approved, you can complete the pull request and delete your branch:

![complete pr](https://github.com/enigmaglass-docs/.github/blob/main/profile/assets/gif/merge-feature-branch-develop.gif)

7. Approve the deployment to the `development` environment:

![approve development deploy](https://github.com/enigmaglass-docs/.github/blob/main/profile/assets/gif/approve-development-deploy.gif)

[![Development Build and Deploy](https://github.com/enigmaglass-docs/enigmaglass/actions/workflows/deploy-dev.yml/badge.svg?branch=development)](https://github.com/enigmaglass-docs/enigmaglass/actions/workflows/deploy-dev.yml)

8. Verify that your changes are correct and the site is functioning as it should in the `development` environment:

![view dev site](https://github.com/enigmaglass-docs/.github/blob/main/profile/assets/gif/view-dev-site.gif)

9. Create a pull request to promote your changes from `development` to `main` to update the production site:

![dev to main pr](https://github.com/enigmaglass-docs/.github/blob/main/profile/assets/gif/dev-to-main-pr.gif)

10. Once all tests have passed and your pull request has been approved, complete the pull request:

![complete pull request into main](https://github.com/enigmaglass-docs/.github/blob/main/profile/assets/gif/complete-pull-request-into-main.gif)

11. Approve the production deployment to the `github-pages`environment:

![approve prod deploy](https://github.com/enigmaglass-docs/.github/blob/main/profile/assets/gif/approve-prod-deploy.gif)

[![pages-build-deployment](https://github.com/enigmaglass-docs/enigmaglass/actions/workflows/pages/pages-build-deployment/badge.svg)](https://github.com/enigmaglass-docs/enigmaglass/actions/workflows/pages/pages-build-deployment)

12. Verify that your changes were successfully deployed to the production `github-pages` environment:

![verify prod deploy](https://github.com/enigmaglass-docs/.github/blob/main/profile/assets/gif/verify-prod-deploy.gif)

That's it! You've successfully update the site!