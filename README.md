<!-- Title -->
<h1 align="center">
PECES R Modules
</h1>

<!-- description -->
<p align="center">
  <strong>R Teaching modules for teaching programming and earth science concepts. Developed during Programming in Earth Science Classroom Educational Workshop (PECES). </strong>
</p>

<!-- Information badges -->

<p align="center">
  <span style="margin-right: 1.5em;">
    <strong>Jupyter + R:</strong>
    <a href="https://mybinder.org/v2/gh/PECES-Initiative/R_Modules/HEAD">
      <img src="https://mybinder.org/badge_logo.svg">
    </a>
  </span>

  <span style="margin-right: 1.5em;">
    <strong>RStudio:</strong>
    <a href="https://mybinder.org/v2/gh/PECES-Initiative/R_Modules/HEAD?urlpath=rstudio">
      <img src="https://mybinder.org/badge_logo.svg">
    </a>
  </span>
</p>


During PECES 2026, we developed a series of R teaching modules to introduce key programming and data science concepts. This repository is meant to be a growing list of activities that teachers can use and add to. We hope that these modules can be useful in classes and provide inspiration for further modules.

A similar set of [R teaching modules are available at a sister repository](https://github.com/PECES-Initiative/Python_Modules).

# Using the Modules

Feel free to use these modules however you want! You can use them directly in your class. The easiest way to do this, with no setup, is to simply launch binder. You can click on either of the badges above, or follow these links:

- Jupyter + R: https://mybinder.org/v2/gh/PECES-Initiative/R_Modules/HEAD
- RStudio: https://mybinder.org/v2/gh/PECES-Initiative/R_Modules/HEAD?urlpath=shiny/bus-dashboard/

This will launch off the notebooks within a web broweser for interactive use. Any changes are not saved, but the environment is automatically set up. Updated notebooks can be downloaded. 

Another option would be to fork this repository, which will make a copy in your personal Github account. You will be able to update it with any newly added modules over time. You can then adapt any modules, or distribute them to students another way (RStudio, Quatro, etc.).

For more information on Binder, and how it automatically sets up the environment, see the Binder section below.

# Adding New Modules

1. Fork this repository! This will make a copy of this repository in your personal GitHub account. [Here are instructions!](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/working-with-forks/fork-a-repo)
2. [Clone](https://github.com/git-guides/git-clone) the repository locally on your computer. In the terminal, go to the location you want the repository to be located and type:
  ```
  git clone git@github.com:PECES-Initiative/R_Modules.git
  ```

2. Make a branch! Pick a branch name, for example `sea_ice_module`. In the terminal type (but replace with your branch name):
  ```
  git switch -c sea_ice_module
  ```

3. You can now add in your module (which should be a R notebook `.Rmb` or a `.ipynb` file) and any other content within your local copy. If you are adding any supplementary material other than a notebook, please make a sub-folder with your module name and add in your content.

4. Git [add](https://github.com/git-guides/git-add), [commit](https://github.com/git-guides/git-commit), and [push](https://github.com/git-guides/git-push) your content. Write your own commit message. Here In the terminal type:
  ```
  git add .
  git commit -m "Adding sea ice module - WRITE YOUR OWN DONT COPY THIS"
  git push
  ```

5. Your code is now on your branch on your copy of the GitHub repository! Repeat Step 4 as you keep adding new content or updating your module! See below in the Binder section about how to keep track of what packages you use! 

6. When you module is done, open a Pull Request (PR) so that your module can be added to the main Github organization (since it is just on your fork right now!). [Here is step by step guide of how to open a PR](https://github.blog/developer-skills/github/beginners-guide-to-github-creating-a-pull-request/). Make sure you have completed the PR checklist that shows up once you have made the PR.

7. An administrator will check your module and approve your pull request!

8. You're done! Thank you for contributing! 

# Using Binder with R

Binder supports using R and RStudio, with libraries pinned to a specific
snapshot on [packagemanager.rstudio.com](https://packagemanager.rstudio.com/client/#/).

## Requirements and suggestions

You need to have a `runtime.txt` file that is formatted like:

```
r-<r-version>-<YYYY>-<MM>-<DD>
```

where `<r-version>` is a version of R (like 4.1, 4.0, etc) you want to use,
and `<YYYY>-<MM>-<DD>` is the date for [a snapshot](https://packagemanager.rstudio.com/client/#/repos/1/overview)
from [packagemanager.rstudio.com](https://packagemanager.rstudio.com) that will
be used for installing your R packages.

Try using a date newer than `2022-01-01`, as you'll get faster
package installs thanks to [binary packages](https://www.rstudio.com/blog/package-manager-v1-1-no-interruptions/)
from rstudio.packagemanager.com!

To install R libraries, add `install.package("<package-name>")` calls to
`install.R`. If you want to pin to a specific version of the library, you
can also do `devtools::install_version("<package-name>", "<version>")`.

For some R packages, you might need to install system packages via apt - you can
do so by writing out a list of apt package names in `apt.txt`. You can find
the list of such packages in the page for your package at
[packagemanager.rstudio.com](https://packagemanager.rstudio.com/client/#/). Make sure
to select "Ubuntu 18.04 (Bionic)" in the dropdown on the top right.

Both [RStudio](https://www.rstudio.com/) and [IRKernel](https://irkernel.github.io/)
are installed by default, so you can use either the Jupyter notebook interface or
the RStudio interface.

This repository also contains an example of a [Shiny app](https://github.com/binder-examples/r/tree/main/bus-dashboard).

## Alternatives

There are many ways to use R in mybinder.org!

**[rocker/binder](https://github.com/rocker-org/binder/)** - this uses a base image from the R community's
excellent [rocker project](https://www.rocker-project.org/) - you get a lot of curated base
packages, faster binary package installs as well as ability to pin to a specific version of R (>4.0).

**[r-conda](https://github.com/binder-examples/r-conda)** - mybinder.org also
supports using the [conda](https://conda.io) package manager to manage R and R packages.
This gives you access to specific R versions as well as fast installs of R
packages available in [conda-forge](https://conda-forge.org/)

Another alternative is to use the [holepunch package for R](https://karthik.github.io/holepunch/articles/getting_started.html).

## URL addresses for RStudio and Shiny environments

The Binder repository can be used to allow anyone to access an RStudio environment containing our code and data right
in their web browser. It also allows hosting a Shiny app. For those purposes, we have to append a bit of text to the
URL of our Binder repository, which we can find out at [mybinder.org](https://mybinder.org/) when we enter
the URL of our original repository from GitHub or Figshare, etc.

- For the RStudio environment, we must add the following at the end of the URL: `?urlpath=rstudio`

  - Example: http://mybinder.org/v2/gh/binder-examples/r/main?urlpath=rstudio

- For the Shiny app environment, we must add the following at the end of the URL: `?urlpath=shiny`. In this case, we
also have to note that if the Shiny app files are located in a folder, this folder should be specified in the URL,
after a slash. We would then also have to put in a trailing slash at the end of the URL, and to avoid spaces in the
name of the repository, placing instead a hyphen (the reason is that spaces are converted to `%20`).

  - Example: http://mybinder.org/v2/gh/binder-examples/r/main?urlpath=shiny/bus-dashboard/
