# Practical scRNA-seq Analysis with R — ready-made environment

A one-click environment for the [course](https://learn.chatomics.com/courses/practical-scrnaseq-analysis-with-r): R 4.4, Bioconductor 3.19, RStudio Server, every package the chapters use, and the course data downloaded on first start.

## In the browser (GitHub Codespaces)
1. Click **Use this template → Create a new repository** (so your work is saved in your own repo), then on your copy click **Code → Codespaces → Create codespace on main**. Choose the **4-core / 16 GB** machine — single-cell analysis needs the memory.
2. Wait for the data download to finish (`data-download.log` in the file list; about 2.5 GB, a few minutes).
3. RStudio opens automatically in a new tab (port 8787; no login). If it doesn't, open the **Ports** panel and click the globe next to **RStudio**. In RStudio, open `scrnaseq-course.Rproj`.
4. Log in to the course at https://learn.chatomics.com/scrnaseq/ and use **Download the code (zip)** in the page footer. Unzip it into this folder: `qmd/` has the chapters, `R/` the plain R scripts.

GitHub's free tier gives personal accounts 120 core-hours a month (about 30 hours on a 4-core machine). Stop the codespace when you're done (it also auto-stops after 30 minutes of inactivity).

## On your own computer
You don't need this repo. Install R ≥ 4.3 and RStudio, then from your project folder run `bash download-data.sh` (or `source("download-data.R")` in R) to fetch the data, and install the packages — `renv.lock` has the exact versions (`install.packages("renv"); renv::restore()`), or install them with `BiocManager::install()` as each chapter shows.

## What's in here
- `.devcontainer/` — the Dockerfile that builds the image (`ghcr.io/crazyhottommy/scrnaseq-course-env`) and the Codespace settings
- `download-data.sh` / `download-data.R` — download + verify the course data into `data/`
- `renv.lock` — the package versions that built the course pages
- `scrnaseq-course.Rproj`, `.here` — so `here()` and relative paths behave like in the chapters

The course content itself is for enrolled students and is not in this repository.
