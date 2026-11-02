> ⚠️ Due to occasional updates, this README file might be out of date with the latest instructions. Please refer to the [Original Repository README file](https://github.com/Cornell-MAE-UG/portfolio/blob/main/README.md) for up-to-date instructions.

# Portfolio Instructions

This is a template for you to start building your professional portfolio. It is also part of your journey at MAE and will be reviewed, as needed, by your instructor and the Undergraduate Program Office.

This is your personal copy of the portfolio template repository. It was created automatically when you accepted the Assignment through the GitHub Classroom link you were provided. Once you are up and running, you can delete this README file or replace it with your own content if you wish. 

In the following sections, you will find instructions on how to edit, test, and publish your portfolio.

## Portfolio Editing Workflow

It's important to understand the logic of the workflow to edit and publish your portfolio. The process goes as follows:

1. Once: **Create a working copy** of your portfolio.
Your portfolio is initially stored on GitHub. You _could_ edit it directly on there, but this is inconvenient, inefficient, and error-prone. 
> In a realistic work setting, you would never edit code directly on a server.
2. On you working copy, you **edit any relevant files**, add images, new project pages, text, etc. 
Remember to [commit](https://docs.github.com/en/get-started/using-git/about-git#basic-git-commands) often to save your progress. 
3. Once you made changes, **test out your portfolio by running a local test webserver** and see if it looks as planned.
4. If you're happy, make sure everything is committed and **push your changes to Github**. Then publish your portfolio through GitHub Pages.
> Once your portfolio is live on the internet, every time you push new changes, GitHub will publish your updated portfolio to the Internet. This usually takes a few minutes before it is live. Make sure you understand which edits are local to your working copy and which are pushed (sent to) the central repository on GitHub and thus public. Also, make sure you understand when you are looking at the portfolio on your local test server and when you are viewing the live version on GitHub Pages.
5. Rinse and repeat from Step 2 above. 

We will go through each of these steps in the following sections. 

---

## Step 1: Creating a Working Copy

You will set up your local copy on an online [Codespaces](https://github.com/features/codespaces) environment for development. You create a Codespace through the "Code" button as shown in the image below. This starts an online server with a development environment that enables you to edit, test, commit, and push your work.

<img src="assets/images/codespace-button.png" width="400" />

Note that editing, saving, and committing on Codespaces is not the same as editing directly on GitHub. When you make changes on Codespaces, you still need to commit and push your changes to GitHub to publish them online. Also, when you run a test server on Codespaces, it is running a temporary server that you can use to debug, but it is not considered "published" until you push your changes to GitHub.

#### For Advanced Users

For more efficient operation, you can clone the code to your own laptop using a tool like [Visual Studio Code](https://code.visualstudio.com/). You can use VS Code for editing, committing, testing, and other git commands. If you do so, you might need to work around some configuration issues which are automatically solved on the Codespace machine, but the upside is that you can work offline and do changes and preview them faster.

If you have experience with command lines on terminals, you can also use the git command line interface (CLI) to maintain your local copy and use whatever editor you want to edit your portfolio.

Please refer to the [Jekyll](https://jekyllrb.com/) and [GitHub Pages](https://pages.github.com/) documentation for more advanced usage.

---

## Step 2: Editing the Files to Personalize Your Portfolio


Let's get you up and running with some basic edits to personalize your portfolio.
> No need to keep the `< >` brackets. They are just there to indicate placeholders.

### Name

Change any references to `Your Name` or `<Your Name>` to your actual name in the following files:
- `_config.yml`
- `index.md`
- `_pages/projects.md`
- `_pages/cv.md`


### Homepage
- In `index.md`: Replace the placeholder text with a welcome or pitch paragraph about yourself.
- Replace the placeholder image `assets/images/profile-pic.jpg` with a portrait of yourself.

### Projects
- In the `_projects` folder: Use the provided example pages (e.g., `2022-trig-analysis.md`) to build one page per project.
- Each project has a main (square) project image, set in the page's top matter by the `image` variable in the preamble on the top of the page (the part between the `---` lines).
- All images are in `assets/images`. Delete the ones you don't need.
- It is useful to name the page with a leading date. This will determine the order of projects on your main portfolio gallery. You can also develop another ordering by naming the projects with some numerical prefix.
- The example project pages show you how to include code and images in the portfolio page.
- Refer to the [Jekyll Markdown documentation](https://jekyllrb.com/docs/markdown/) for other formatting tips.
- Delete the example project pages when you are done.

### CV
- Replace the placeholder `assets/CV.pdf` with your own PDF CV.
- You can either edit or delete the placeholder CV markdown text. This is up to you

### Color Schemes

The provided template comes with multiple color schemes. To choose a scheme:

1. Open the `_config.yml` file.
2. Look for the `color_scheme` setting.
3. Change the value to the desired skin name. Refer to the inline comment in `_config.yml` for available skin options.


Example:
```yaml
skin: aqua
```
Make any other changes you would like to your portfolio. You can edit the `sass/custom.scss` file to change colors, fonts, and other styling options.

### Commit Your Changes

After making changes, remember to commit them often to save your progress. In the terminal, run the following commands:

```bash
git add .
git commit -m "<Commit Message>"
```

Write a meaningful commit message that describes the changes you made.
On VS Code or Codespaces, you can also use the Git interface inside the development environment to stage (add) and commit your changes. The Git interface usually shows up as a small branch icon on the left sidebar. You can learn how to use it [here](https://code.visualstudio.com/docs/editor/versioncontrol).

---

## Step 3: Running the Site Locally for Testing

Once you made your changes, or at any time you wish to, you can test your changes by running a local web server, using the `bundle` command. All of this happens **in the terminal** on Codespaces, or, for advanced users in VS Code or directly in your terminal app.

By default, the terminal is at the bottom of the Codespace. If it was closed or hidden for some reason, you can open the terminal in your codespace by going to the top left menu (three horizontal lines) and selecting `Terminal -> New Terminal`.

### Install Packages (once)

You only need to run this command the first time you try to run jekyll, to install the relevant packages: 
```bash
bundle install
```

### Running the Local Portfolio Server
Then, to run the server you run the `jekyll serve` command:
```bash
bundle exec jekyll serve --baseurl=""
```

Note that many updates to your code are automatically reloaded into the web server. However, some changes, notably to `_config.yml` require a restart of the jekyll server.

You can access the site at the URL shown by the `serve` command. It looks something like this:
```python
    Server address: http://127.0.0.1:4000/
  Server running... press ctrl-c to stop.
```

On both Codespace and your laptop, you can Cmd-click (Mac) or Ctrl-click (Windows) the URL to open it in a new browser tab. On your laptop, you can also just open your browser and go to `http://localhost:4000/`.

---

## Step 4: Publishing your Portfolio to the Web

Remember, your portfolio is not live on the web until you push your changes to GitHub and set up GitHub Pages. What you are viewing on your local test server is only on your local machine (or Codespace) and neither permanent nor visible to the public.

### Push your Changes to GitHub

Once everything looks good, commit and push your changes. In the terminal, run the following commands. Ideally, you would have added and committed many times locally before pushing to Github.

```bash
git add .
git commit -m "<Commit Edit>"
git push origin main
```

In VS Code or Codespaces, you can use the Git interface inside the development environment to stage (add), commit, and push your changes.

### Set Up GitHub Pages

Finally, for publishing your portfolio, follow these steps:

1. In your `_config.yml` file, set the `baseurl` to your portfolio repo name (e.g., `"/sp26-portfolio-hoffman/"`). Commit and push this change to GitHub.

```yaml
baseurl: "/<your-repo>/"
```

2. Go to your repository's Settings
<img src="assets/images/settings.png" width="600" />

3. Choose the "Pages" tab under "Build and Deployment", verify that "Source" says "Deploy from a branch" and under "Branch" choose `main` and `/ (root)`
<img src="assets/images/pages-settings.png" width="600" />

4. Don't forget to save this setting at the bottom of the page.

### Your Published Portfolio Site
After a few minutes, your portfolio should be live at `https://cornell-mae-ug.github.io/<your-repo>/`, where `your-repo` is this repository's name, probably `portfolio-<your-github-username>`. This URL is also shown in your Pages setting tab.

:tada:

**You can now replace this template README file with a more informative text**, but check out additional tips and tricks below.

### More Control over Publishing

If you add plugins and add-ons, you might need to publish using your own Gemfile, and other custom actions. See the following link to learn everything about [publishing a Jekyll site with Github Pages](https://jekyllrb.com/docs/continuous-integration/github-actions/).

---

## Advanced Customization: Using Other Jekyll Themes

You can change the style of any component of the portfolio editing the `custom.scss` file, which is written in the [Sass](https://sass-lang.com/) language.

In addition, as mentioned, your portfolio uses [Jekyll](https://jekyllrb.com/) underneath the hood. For more advanced styling of your portfolio, check out [this documentation](https://docs.github.com/en/pages/setting-up-a-github-pages-site-with-jekyll).

This also means that you can customize your portfolio to a greater extent by using other Jekyll themes. Here are some good places to find themes:

- [Jekyll Themes on GitHub](https://github.com/topics/jekyll-theme)
- [Start Bootstrap](https://startbootstrap.com/themes/jekyll/)
- [Jekyll Themes](https://jekyllthemes.io/)

Follow the theme's installation and customization instructions as needed to fit your portfolio content.

## Tips and Tricks

### Commenting Out Content

You can comment out a bit of text or an image by using the `{% comment %}` command:

```ruby
{% comment %}
    Stuff you want to comment out.
{% endcomment %}
```

### Changing the text width

Change any styling by editing the `custom.scss` file, a Sass file, which is a superset of CSS.

For example, change the text width by changing the `max-width` of `.container`:

```css
.container {
  max-width: 1000px;
}
```
