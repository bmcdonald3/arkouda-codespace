# Introduction to Arkouda

[Arkouda](https://bears-r-us.github.io/arkouda/) is a framework for interactive Data Analytics at supercomputing scale, but is highly extensible, so can be thought of as a framework for running any parallel, distributed code from Python that you can dream up!

This repository contains code from the [ChapelCon 2024](https://chapel-lang.org/ChapelCon24.html) Chapel tutorial, however, anyone can work out of this Codespace to get familiar with Arkouda! It includes configuration files, data files, and Jupyter notebooks demonstrating a sample Arkouda workflow related to the tutorial.

If you'd like to follow along with the recorded tutorial from ChapelCon, please [click here](https://www.youtube.com/watch?v=__pXYW359Ws).

## Who is this tutorial for? What can I learn from this tutorial?

This tutorial is designed for individuals interested in exploring the capabilities of Arkouda, a framework for interactive data analytics at supercomputing scale while working with a real-world data set. The tutorial is particularly suitable for:

* Data scientists and analysts seeking to leverage high-performance computing for their projects.
* Developers interested in learning about parallel and distributed programming using Python.
* Researchers exploring the application of Arkouda in various domains.

By completing this tutorial, you will gain a solid understanding of:

* The core concepts and features of Arkouda.
* How to use Arkouda to perform data analysis and manipulation tasks efficiently.
* The benefits of using Arkouda for large-scale data processing.
* How to integrate Arkouda with other tools and libraries.

This tutorial will equip you with the knowledge and skills needed to effectively utilize Arkouda for your data-intensive projects. Beyond that, additional resources are provided for those who would like to take Arkouda to a supercomputer or learn more about the API.

## Getting started

When getting started with this Codespace, we recommend one of two options:

* Clean Slate: Start with `clean_tutorial_nyc_taxi_parquet.ipynb` if you prefer a blank workspace.
* Inspect the Output: Use `tutorial_nyc_taxi_parquet.ipynb` to see the notebook with pre-executed code and explore the results.

## Using a Codespace

> :warning: Because Codespaces are a virtualized environment running on shared hardware with a modest core count, don't expect parallelism or performance observed here to be reflective of what a native installation of Chapel can achieve.

This repo includes a `devcontainer.json` file, making it usable from GitHub Codespaces. When viewing this repository from GitHub's UI, click __Use this template > Open in a codespace__ to get started. 

Once your codespace has been launched, the Arkouda server will automatically be started on forwarding port `5555` and a Jupyter server will be hosted on forwarding port `8888`.

In the terminal at the bottom of the VisualStudio window, clicking the `PORTS` tab at the bottom will show you where you can access your Jupyter notebook. By right-clicking on the `Forwarded Address` for the Jupyter server running on port `8888`, you can visit that link to get started with your Jupyter notebook.

Once you are seeing the Jupyter server screen, you can open the `clean_tutorial_nyc_taxi_parquet.ipynb` file and start running your Jupyter notebook!

## Learning Resources
To learn more about Arkouda and take your applications to a supercomputer, consider the
 following resources:

* [Arkouda repository](https://github.com/bears-r-us/arkouda)
* [Arkouda documentation](https://bears-r-us.github.io/arkouda/index.html)
* [Arkouda API Reference](https://bears-r-us.github.io/arkouda/autoapi/index.html)
* [Arkouda examples](https://bears-r-us.github.io/arkouda/examples.html)
* [Arkouda-contrib repository](https://github.com/Bears-R-Us/arkouda-contrib)
