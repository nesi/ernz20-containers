---
title: "Introduction to containers"
teaching: 10
exercises: 0
questions:
objectives:
- Learn what are containers and how they are beneficial to HPC & Cloud computing
---


### Containers vs Virtual Machines

A container is an entity providing an isolated software environment (or filesystem) for an application and its dependencies.

If you have already used a Virtual Machine, or VM, you're actually already familiar with some of the concepts of a container.

<!-- ![Containers vs. VMs]({{ page.root }}/fig/container_vs_vm.png) -->
<img src="{{ page.root }}/fig/container_vs_vm.png" alt="Containers vs. VMs" width="619" height="331"/>

The key difference here is that VMs virtualise **hardware** while containers virtualise **operating systems**.  There are other differences (and benefits), in particular containers are:

* lighter weight to run (less CPU and memory usage, faster start-up times)

* smaller in size (thus easier to transfer and share)

* modular (possible to combine multiple containers that work together)


### Containers and your workflow

There are a number of reasons for using containers in your daily work:

* Data reproducibility/provenance
* Cross-platform portability
* Simplified collaboration
* Simplified software dependencies and management
* Scalability
* Consistent testing environment

A few examples of how containers are used at NeSI:

* Bioinformatics workflows
* Machine Learning 
* Python apps in climate and earth systems
* GIS data-processing workflows
* RStudio & Jupyter Notebook sessions
* Webservers
* Desktop environments

Here's an overview of what a typical workflow looks like:

<!-- ![Container Workflow]({{ page.root }}/fig/container_lifecycle.png) -->
<img src="{{ page.root }}/fig/container_lifecycle_nesi.png" alt="Container Workflow" width="716" height="298"/>


### Terminology

An **image** is a file (or set of files) that contains the application and all its dependencies, libraries, run-time systems, etc. required to run. You can copy images around, upload them, download them etc.

A **container** is an instantiation of an image.  That is, it's a running process spawned out of an image.  You can run multiple containers from the same image, much like you might run the same application with different options or arguments.

In general, an image corresponds to a file, a container corresponds to a process.

A **registry** is a server application where images are stored and can be accessed by users. It can be public (e.g. Docker Hub) or private.

To build an image we need a recipe. A recipe file is called a **Definition File**, or **def file**, in the *Singularity* jargon and a **Dockerfile** in the *Docker* world.


### Container engines

A number of tools are available to create, deploy and run containerised applications. Some of these will be covered throughout this tutorial:

* **Docker**: the first engine to gain popularity, still widely used in the IT industry. Not very suitable for HPC as it requires *root* privileges to run. We'll use it mostly to build container images.

* **Singularity**: a simple, powerful container engine for the HPC world. The main focus of this workshop.

* **Shifter/Sarus**: a Docker-compatible container engine, suitable for HPC. Can run containers, cannot build them.

* **Charliecloud**: a Docker-compatible tool for lightweight, user-defined software stacks for high-performance computing.

* **Enroot**: Nvidia's take on containers, a simple, yet powerful tool to turn traditional container/OS images into unprivileged sandbox    es.

* **Podman**: a root-less alternative to Docker. Misses on some features for HPC.
