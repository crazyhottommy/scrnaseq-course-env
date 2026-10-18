# Practical scRNA-seq Analysis with R — course environment (R 4.4 / Bioconductor 3.19, RStudio Server)
FROM bioconductor/bioconductor_docker:RELEASE_3_19

# Course packages (binary installs from Bioconductor's container repo where available), then the two GitHub-only ones.
RUN Rscript -e 'BiocManager::install(c("ComplexHeatmap", "DESeq2", "DropletUtils", "ExperimentHub", "Seurat", "SingleCellExperiment", "SingleR", "UCell", "celda", "celldex", "circlize", "clusterProfiler", "dplyr", "enrichplot", "fishpond", "genefilter", "ggplot2", "harmony", "here", "knitr", "msigdbr", "org.Hs.eg.db", "purrr", "rmarkdown", "rtracklayer", "scCustomize", "scDblFinder", "scater", "sessioninfo", "stringr", "tibble", "tictoc", "tidyr"), ask = FALSE, update = FALSE, Ncpus = 4)' \
 && Rscript -e 'remotes::install_github(c("immunogenomics/presto", "rnabioco/clustifyr"), upgrade = "never")' \
 && Rscript -e 'ok <- vapply(c("ComplexHeatmap", "DESeq2", "DropletUtils", "ExperimentHub", "Seurat", "SingleCellExperiment", "SingleR", "UCell", "celda", "celldex", "circlize", "clusterProfiler", "clustifyr", "dplyr", "enrichplot", "fishpond", "genefilter", "ggplot2", "harmony", "here", "knitr", "msigdbr", "org.Hs.eg.db", "presto", "purrr", "rmarkdown", "rtracklayer", "scCustomize", "scDblFinder", "scater", "sessioninfo", "stringr", "tibble", "tictoc", "tidyr"), requireNamespace, logical(1), quietly = TRUE); if (!all(ok)) stop("missing: ", paste(names(ok)[!ok], collapse = " ")); cat("all course packages installed\n")' \
 && rm -rf /tmp/downloaded_packages /tmp/Rtmp*

# RStudio Server without a login page, running as the rstudio user, opening the course folder.
RUN printf 'auth-none=1\nserver-user=rstudio\n' >> /etc/rstudio/rserver.conf \
 && printf 'session-default-working-dir=/workspaces/scrnaseq-course-env\nsession-default-new-project-dir=/workspaces/scrnaseq-course-env\n' >> /etc/rstudio/rsession.conf \
 && echo "rstudio ALL=(ALL) NOPASSWD:ALL" > /etc/sudoers.d/rstudio && chmod 0440 /etc/sudoers.d/rstudio
ENV DISABLE_AUTH=true
