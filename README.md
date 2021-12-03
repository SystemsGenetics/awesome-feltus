# awesome-feltus

A guide to being awesome in the Feltus lab. Think of this page as a central hub that can help you get to wherever you need to go. Inspired by [cufctl/mlbd](https://github.com/CUFCTL/mlbd) and [sindresorhus/awesome](https://github.com/sindresorhus/awesome).

## Introduction

Everyone in the Feltus lab is welcome to contribute to this guide, and to shape what it means to be awesome in the Feltus lab. I (Ben) am a software engineer, so I view awesome-ness through the lens of an engineer, but the Feltus lab is made up of engineers, scientists, and people in between, so I hope that in time this guide will reflect a holistic view of how to be awesome in the Feltus lab.

For now, this guide will show you around all of the fancy technology at your disposal, and give you tips on how to use them effectively. This guide will reference several pages from the [ML/BD Creative Inquiry website](https://cufctl.github.io/mlbd/) because I already wrote a bunch of this stuff over there.

## Getting Started

We use a lot of different technologies in the Feltus lab. The first step is to just know what they are.

First, the web applications you will use most often for your work:

- [FeltusLab Slack](https://feltuslab.slack.com/): The website we use to communicate with each other. You'll still have to use email, but Slack will make things a bit easier.
- [GitHub](https://github.com/): That's where you are now! We put all of our code repositories here. Most of the lab's projects are [here](https://github.com/systemsgenetics). You can also make an account and store personal projects here.
- [Overleaf](https://www.overleaf.com/): A website for creating LaTex documents for things like research papers. You'll want to learn how to write in LaTeX, and you'll want to do it through Overleaf.
- [Palmetto](https://www.palmetto.clemson.edu/): Clemson's supercomputer, the place where you will do most of your work. They also do tours! See the Palmetto section below.

Second, the software tools you will use, mostly within Palmetto. Feel free to peruse the links, but they are mostly for reference. You will learn these tools by using them:

- [Anaconda](https://anaconda.org/): A package manager for Python and R packages. The command line tool is `conda`. You will want to learn how to use this tool.
- [Bash](https://www.gnu.org/software/bash/): You probably use Windows or Mac. Well, Palmetto uses [Linux](https://linux.org/). And Bash is the language of Linux. You will want to get very good at Bash. Here is a [guide](https://devhints.io/bash).
- [Docker](https://www.docker.com/): A tool for building and running containers. You might end up using it directly. Hopefully you won't have to. But it's good to know.
- [Git](https://git-scm.com/): A tool for maintaining code. Quit leaving your code all over the place and use version control! See GitHub above.
- [Jupyter](https://jupyter.org/): A suite of tools for running code in an interactive "notebook". You will want to learn how to play with code this way.
- [Kubernetes](https://kubernetes.io/): A container orchestration system. You probably won't have to use this one directly, but Feltus is really excited about it, so you should probably know what it is.
- [Nextflow](https://nextflow.io/): A programming language and a tool for running workflows. You'll understand why it's important later.
- [Python](https://www.python.org/): The programming language that everyone else uses for data science, so you probably should too. You could also use [R](https://www.r-project.org/) but it's not as cool. You should not use [Perl](https://www.perl.org/).

## Palmetto

The [Palmetto cluster](https://www.palmetto.clemson.edu/) is Clemson's supercomputer. Starting out, you will do most of your work there, so it's important that you know how to use it well. Refer to [this page](https://cufctl.github.io/mlbd/skills/palmetto-cluster.html) for more information about Palmetto. Refer to [this page](https://cufctl.github.io/mlbd/skills/getting-started.html) for the process that my CI students use to get familiar with Palmetto and JupyterLab.

__Access__
- [Palmetto OnDemand](https://openod02.palmetto.clemson.edu/): The superior way to access Palmetto, do everything in your browser.
- SSH: The inferior way to access Palmetto: `ssh <username>@login.palmetto.clemson.edu`

__Nodes__
- Login node: Entrypoint for SSH access. You don't really need it now that we have Palmetto OnDemand. But if you do use it, you can only browse files or submit jobs with `qsub`.
- [Login VM](http://palmetto.clemson.edu/loginvm): Like your own personal login node. Use it whenever you need to run Nextflow pipelines at scale on Palmetto.
- Compute nodes: Used for everything else. There are old nodes and new nodes, GPU nodes, big memory nodes... you get the idea.

__Storage__
- `/home/${USER}`: Your home directory, and your starting location when you log in. You get 100 GB of space, so use it wisely.
- `/scratch1/${USER}`: The big scratch directory. It currently has 2 PB of space, but it is shared by everyone on Palmetto, and files older than 3 months get deleted. I accidentally filled up scratch1 once. One day, if you're lucky, you will too.
- `/zfs/lasernode/feltuslab`: The ZFS directory shared by the Feltus lab. It currently has 75 TB and we're currently using about half of that. Make a folder with your username and use that like your home directory, just don't go crazy.

Here is the recommended way for you to use Palmetto, for your own personal sanity:
- __Access__: Use Palmetto OnDemand, provision a JupyterLab instance and do everything from there.
- __Nodes__: Use the login node or a Login VM to submit batch jobs, use OnDemand and JupyterLab for interactive jobs.
- __Storage__: Use your home directory and the ZFS directory to store code and input/output data. Use the scratch directory to run jobs, but don't leave anything there that you intend to keep.

Here are some things you should __not__ do:
- Use the login node for anything other than browsing files and submitting batch jobs (use JupyterLab instead)
- Perform long-running tasks on an interactive node via SSH (use JupyterLab instead)
- Downloading images from Palmetto so that you can view them (use JupyterLab instead)

As you can see, the solution to many potential problems is to use JupyterLab.

## Other Compute Environments

You may be sent to explore other environments aside from Palmetto, including:
- [Amazon Web Services](https://aws.amazon.com/)
- [Google Cloud Platform](https://cloud.google.com/)
- [Nautilus](https://nautilus.optiputer.net/)

Don't be frightened. If and when that time comes, you will be equipped with the tools to use these platforms without having to be a Kubernetes or cloud expert. That is all I will say for now.

## GitHub Repositories

We have created a bunch of bioinformatics tools that aid us in the process of scientific discovery. Most of these tools are housed in the [SystemsGenetics](https://github.com/systemsgenetics) org, which we manage alongside our friends at the [Ficklin lab](http://ficklinlab.cahnrs.wsu.edu/) at WSU. Some notable tools include:
- [GEMmaker](https://github.com/SystemsGenetics/GEMmaker)
- [GEMprep](https://github.com/SystemsGenetics/GEMprep)
- [Gene Oracle](https://github.com/SystemsGenetics/gene-oracle)
- [KINC](https://github.com/SystemsGenetics/KINC-nf)
- [TSPG](https://github.com/ctargon/TSPG)

Most of these tools are Nextflow pipelines, but you can use the underlying scripts directly as well. One day you might come up with an idea for your own tool or pipeline, so you might want to learn how to write a Nextflow pipeline. Here is a [tutorial](https://github.com/bentsherman/nextflow-palmetto-demo) I made to show you how to do this from a collection of PBS scripts, which is probably what you'll have at that point. Check out the last part of the tutorial for best practices when running Nextflow pipelines on Palmetto.
