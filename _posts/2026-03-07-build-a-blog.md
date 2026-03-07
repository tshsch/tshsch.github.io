---
layout: post
title:  "Build a Blog"
date:   2026-03-07 22:07:06 +0800
categories: jekyll update
---

### Create a repository for your site

1. Create a new repository called `username.github.io` with `README.md`, replacing username with your username in GitHub.
2. Go to **Settings**->**Pages**.

   ![Screenshot of Build and deployment](/assets/images/Image-1.png)

   *Notes on inserting images: Jekyll by default doesn't copy assets placed in the `_posts` folder. Place it in another folder (not something with `_`). For example, create `/assets/images/` in the root of your project and place the image there.*
3. Open `username.github.io`. `README.md` is displayed.

### Create your site with Jekyll

1. Open Git Bash.
2. Navigate to the location where you want to store your site's source files.

   ```bash
   cd FOLDER-NAME
   ```

3. Initialize a local Git repository.

   ```bash
   git init REPOSITORY-NAME
   > Initialized empty Git repository in /REPOSITORY-NAME/.git/
   # Creates a new folder on your computer, initialized as a Git repository`
   ```

4. Change directories to the repository.

   ```bash
   cd REPOSITORY-NAME
   ```

5. Create a new Jekyll site.

   ```bash
   jekyll new --skip-bundle .
   # Creates a Jekyll site in the current directory
   ```

6. Edit the Gemfile that Jekyll created.  
   1. Add "#" to the beginning of the line that starts with `gem "jekyll"` to comment out this line.
   2. Add the `github-pages` gem by editing the line starting with `# gem "github-pages"`. Change this line to:

   ```bash
   gem "github-pages", "~> 232", group: :jekyll_plugins
   ```

7. From the command line, run `bundle install`.

   Use the Tsinghua University mirror. Refer to [Tsinghua University Open Source Mirror Software Site](https://mirrors4.tuna.tsinghua.edu.cn/help/rubygems/).

   ```bash
   # Add the mirror source and remove the default source
   gem sources --add https://mirrors.tuna.tsinghua.edu.cn/rubygems/ --remove https://rubygems.org/
   # List existing sources
   gem sources -l
   # There should be only one source which is the mirror source
   bundle install
   ```

8. Edit the gitignore file that Jekyll created. Ignore the gems lock file by adding this line:

   ```text
   Gemfile.lock
   ```

### Test your site locally

1. Since Ruby 3.0 or later is installed, to eliminate possible error, run `bundle install webrick`, because these versions of Ruby no longer come with `webrick` installed.

2. Run your Jekyll site locally.

   ```bash
   bundle exec jekyll serve
   ```

   An error occured when generating: `No such file or directory @ rb_sysopen - FOLDER-NAME/Generating (Error::ENOENT)`.

   Troubleshooting: The file `Generating...` exists in `FOLDER-NAME`, but when trying to delete it, a message popped up saying the item could not be found.

   Solution: Delete the file `Generating..." by running

   ```bash
   rm -f "Generating..."
   ```

### Final Steps

1. Add and commit your work.

   ```bash
   git add .
   git commit -m 'Initial GitHub pages site with Jekyll'
   ```

2. Add your repository on GitHub.com as a remote.

   ```bash
   git remote add origin https://github.com/USER/REPOSITORY.git
   ```

3. Push the repository to GitHub.

   ```bash
   git push -u origin main
   ```

4. Go to **Settings**->**Pages**->**Visit Site**.

### Reference

[GitHub Docs](https://docs.github.com/en)

[Jekyll Talk](https://talk.jekyllrb.com/)

[Stack Overflow](https://stackoverflow.com/questions)
