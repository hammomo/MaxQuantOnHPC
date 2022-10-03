# MaxQuantOnHPC

A guideline for using MaxQuant to analyze proteomics data on High Performance Computing (HPC) Linux clusters.

## Table of Contents

- [MaxQuantOnHPC](#maxquantonhpc)
  - [Table of Contents](#table-of-contents)
  - [Requirements](#requirements)
  - [MaxQuant Configuration Preparation](#maxquant-configuration-preparation)

## Requirements

* Access to HPC clusters
  * In our case, we use [The Computational Shared Facility 3 in University of Manchester](https://ri.itservices.manchester.ac.uk/csf3/).
* MaxQuant stable version 1.6.2.6
  * Doesn't seem to be archived on [MaxQuant official website](https://www.maxquant.org/) :unamused:).
  * Please contact the author <hanyi.mo@postgrad.manchester.ac.uk> for this package.
* Mono Framework >= 5.4.1 
  * [Mono installation tutorial](https://www.mono-project.com/download/stable/#download-lin).
  * The mono version installed on our HPC is
  `Mono JIT compiler version 5.14.0.177`

## MaxQuant Configuration Preparation

The easiest way to configure parameters (*e.g., fasta files, raw MS file paths, fractions*) is to use **MaxQuant GUI**.

> <s>Ofc, this has to be done on Windows.</s> :unamused: <s>Then if this is really the case, what is the point of [MaxQuant goes Linux](https://doi.org/10.1038/s41592-018-0018-y)?</s> :confused:

According to the [MaxQuant official tutorial](http://coxdocs.org/doku.php?id=maxquant:common:download_and_installation) for Linux environment, once the configuration file (*mqpar.xml*) is ready, you can run MaxQuant with a single command line (:warning:***Only for the latest version***):

`dotnet MaxQuant/bin/MaxQuantCmd.exe mqpar.xml`

For our stable version (v1.6.2.6), the command should be:

`mono MaxQuant/bin/MaxQuantCmd.exe mqpar.xml`

Whilst the relative/absolute paths of the executable file (`MaxQuant/bin/MaxQuantCmd.exe`) and configuration file (`mqpar.xml`) should be adjusted according to your own environment.

Fortunately, the configuration file `mqpar.xml` is in fact a plain markup file written by ***Extensible Markup Language***, consisting of trees of node objectives. It can be edited by any lightweight cross-platform editors (*e.g., Vim, Emacs, VSCode, Sublime Text*).

