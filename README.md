# Black at Mila

**The website of Black at Mila — a community dedicated to supporting and celebrating Black researchers, students, and professionals at [Mila - Quebec AI Institute](https://mila.quebec/).**

Black at Mila creates spaces for sharing ideas, fostering collaborations, mentorship, and advocacy. This site amplifies the voices, research, and contributions of Black members within the Mila community. Our mission is to:

- **Build Community**: Create a supportive network for Black researchers, students, and professionals at Mila.
- **Showcase Excellence**: Highlight the groundbreaking work and achievements of Black members.
- **Promote Diversity**: Advocate for greater representation and inclusion in AI research.
- **Share Knowledge**: Facilitate the exchange of ideas through talks and collaborative projects.

The site is a [Jekyll](https://jekyllrb.com/) static site hosted on GitHub Pages.

To get in touch, email [black@mila.quebec](mailto:black@mila.quebec).

## Site content

- **Members** — the current team and alumni of the Black at Mila community, listed under `_team/` and `_alumni/`.
- Site-wide configuration lives in `_config.yml`, and navigation is defined in `_data/navigation.yml`.
- Files (PDFs, `.zip`, etc.) placed in the `files/` directory are served at `https://blackatmila.github.io/files/<filename>`.

## Running locally

When working on the site, it's useful to preview changes locally before pushing them to GitHub. To work locally you will need to:

1. Clone the repository.

### Using a different IDE
1. Make sure you have ruby-dev, bundler, and nodejs installed.

    On most Linux distributions and [Windows Subsystem for Linux](https://learn.microsoft.com/en-us/windows/wsl/about) the command is:
    ```bash
    sudo apt install ruby-dev ruby-bundler nodejs
    ```
    If you see error `Unable to locate package ruby-bundler`, `Unable to locate package nodejs`, run the following:
    ```bash
    sudo apt update && sudo apt upgrade -y
    ```
    then try running `sudo apt install ruby-dev ruby-bundler nodejs` again.

    On MacOS the commands are:
    ```bash
    brew install ruby
    brew install node
    gem install bundler
    ```
1. Run `bundle install` to install ruby dependencies. If you get errors, delete Gemfile.lock and try again.

    If you see a file permission error like `Fetching bundler-2.6.3.gem ERROR:  While executing gem (Gem::FilePermissionError) You don't have write permissions for the /var/lib/gems/3.2.0 directory.` or `Bundler::PermissionError: There was an error while trying to write to /usr/local/bin.`
    Install Gems Locally (Recommended):
    ```bash
    bundle config set --local path 'vendor/bundle'
    ```
    then try running `bundle install` again. If it succeeded, you should see a folder called `vendor` and `.bundle`.

1. Run `jekyll serve -l -H localhost` to generate the HTML and serve it from `localhost:4000`. The local server will automatically rebuild and refresh the pages on changes to Markdown (*.md) and HTML files, while changes to the core template and configuration (i.e., `_config.yml`) will require stopping and restarting Jekyll.
    You may also try `bundle exec jekyll serve -l -H localhost` to ensure jekyll uses the specific dependencies on your own local machine.

If you are running on Linux it may be necessary to install some additional dependencies prior to being able to run locally: `sudo apt install build-essential gcc make`

## Using Docker

Working from a different OS, or just want to avoid installing dependencies? You can use the provided `Dockerfile` to build a container that will run the site for you if you have [Docker](https://www.docker.com/) installed.

You can build and execute the container by running the following command in the repository:

```bash
chmod -R 777 .
docker compose up
```

You should now be able to access the website from `localhost:4000`.

### Using the DevContainer in VS Code

If you are using [Visual Studio Code](https://code.visualstudio.com/) you can use the [Dev Container](https://code.visualstudio.com/docs/devcontainers/containers) that comes with this repository. Normally VS Code detects that a development container configuration is available and asks you if you want to use the container. If this doesn't happen you can manually start the container by **F1 -> DevContainer: Reopen in Container**. This restarts your VS Code in the container and automatically hosts the site locally on http://localhost:4000. All changes will be updated live to that page after a few seconds.

## Credits

This site was originally built by [Roy Eyono](https://royeyono.com).
