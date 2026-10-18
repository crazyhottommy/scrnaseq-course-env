# Practical scRNA-seq Analysis with R — ready-made environment

[![Open in GitHub Codespaces](https://github.com/codespaces/badge.svg)](https://codespaces.new/crazyhottommy/scrnaseq-course-env?quickstart=1&machine=standardLinux32gb)

One click gives you RStudio in the browser with R 4.4, Bioconductor 3.19, every package the [course](https://learn.chatomics.com/courses/practical-scrnaseq-analysis-with-r) uses, and the course data already downloaded. Nothing to install.

## Start here (about 3 minutes the first time)
1. Click the **Open in GitHub Codespaces** button above (you need a free GitHub account; sign in if asked).
2. Keep the preselected **4-core / 16 GB** machine and click **Create codespace**. Single-cell analysis needs the memory.
3. Wait while the environment starts and the data downloads (~2.5 GB; progress is in `data-download.log`). A new tab with **RStudio** opens by itself. If your browser blocks it, open the **Ports** panel at the bottom, find **RStudio (8787)** and click the globe icon.
4. In RStudio, open the project: **File → Open Project → scrnaseq-course.Rproj**. The `data/` folder is already there.
5. Get the course code: log in at https://learn.chatomics.com/scrnaseq/ and click **Download the code (zip)** in the page footer. In RStudio's **Files** pane click **Upload**, choose `code.zip`, and it unpacks into `qmd/` (the chapters) and `R/` (plain R scripts). Open `qmd/02-quality-control.qmd` and start typing along.

Coming back later: the same button reopens your existing codespace (that's what `quickstart=1` does); starts take about 30 seconds and your files are kept. Codespaces stop by themselves after 30 minutes of inactivity and are deleted after 30 days unused, so download anything you want to keep. GitHub's free tier is 120 core-hours a month, about 30 hours on this machine.

Prefer to own the repo (for example to push your notes to GitHub)? Click **Use this template → Create a new repository** first, then open a codespace on your copy; everything else is identical.

## On your own computer
You don't need this repo. Install R ≥ 4.3 and RStudio, then from your project folder run `bash download-data.sh` (or `source("download-data.R")` in R) to fetch the data, and install the packages — `renv.lock` has the exact versions (`install.packages("renv"); renv::restore()`), or install them with `BiocManager::install()` as each chapter shows.

## What's in here
- `.devcontainer/` — the Dockerfile that builds the image (`ghcr.io/crazyhottommy/scrnaseq-course-env`) and the Codespace settings
- `download-data.sh` / `download-data.R` — download and verify the course data into `data/`
- `renv.lock` — the package versions that built the course pages
- `scrnaseq-course.Rproj`, `.here` — so `here()` and relative paths behave like in the chapters

The course content itself is for enrolled students and is not in this repository.
