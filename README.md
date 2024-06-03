# Introduction to Arkouda

[Arkouda](https://bears-r-us.github.io/arkouda/) is a framework for interactive Data Analytics at supercomputing scale, but is highly extensible, so can be thought of as a framework for running any parallel, distributed code from Python that you can dream up! This repository contains code from the [ChapelCon 2024](https://chapel-lang.org/ChapelCon24.html) Chapel tutorial.

To get started with this template, you can either use [GitHub Codespaces](#using-a-codespace) or your own machine (via [Docker](#using-docker) or by [building from source](#building-arkouda-from-source-on-your-machine)).

In this repository, there are some configuration files, some data files, and some Jupyter notebooks containing a sample Arkouda workflow for the tutorial. If following along in this Codespace, you can start with the `clean_tutorial_nyc_taxi_parquet.ipynb` to have a blank slate or `tutorial_nyc_taxi_parquet.ipynb` to see the same notebook with the code already executed to just inspect the output.

## Learning Resources
To learn about Chapel beyond what's presented in the slides, consider the
 following resources:

* [Arkouda repository](https://github.com/bears-r-us/arkouda)
* [Arkouda documentation](https://bears-r-us.github.io/arkouda/index.html)
* [Arkouda API Reference](https://bears-r-us.github.io/arkouda/autoapi/index.html)
* [Arkouda examples](https://bears-r-us.github.io/arkouda/examples.html)
* [Arkouda-contrib repository](https://github.com/Bears-R-Us/arkouda-contrib)

## Using a Codespace

> :warning: Because Codespaces are a virtualized environment running on shared hardware with a modest core count, don't expect parallelism or performance observed here to be reflective of what a native installation of Chapel can achieve.

This repo includes a `devcontainer.json` file, making it usable from GitHub Codespaces. When viewing this repository from GitHub's UI, click __Use this template > Open in a codespace__ to get started. 

Once your codespace has been launched, the Arkouda server will automatically be started on forwarding port `5555` and a Jupyter server will be hosted on forwarding port `8888`.

In the terminal at the bottom of the VisualStudio window, clicking the `PORTS` tab at the bottom will show you where you can access your Jupyter notebook. By right-clicking on the `Forwarded Address` for the Jupyter server running on port `8888`, you can visit that link to get started with your Jupyter notebook.

Once you are seeing the Jupyter server screen, you can open the `clean_tutorial_nyc_taxi_parquet.ipynb` file and start running your Jupyter notebook!

## Using Docker

Install Docker (see the [Installing Docker](#installing-docker) section below for suggestions). Then, follow the instructions at https://github.com/Bears-R-Us/arkouda-contrib/tree/main/arkouda-docker for an Arkouda install. For a build on your laptop, I would recommend the [Arkouda Full Stack](https://github.com/Bears-R-Us/arkouda-contrib/blob/main/arkouda-docker/arkouda-full-stack) image.

## Building Arkouda from Source on Your Machine

Please follow the instructions on the [Arkouda Build](https://bears-r-us.github.io/arkouda/setup/BUILD.html) page to build the Arkouda server and install the Python frontent dependencies.

When built from source, you will have to manually launch the Arkouda server on your machine:
```bash
./arkouda_server -nl 1
```

To make use of multiple nodes (or to simulate multi-node execution), please
refer to [Multilocale Chapel Execution](https://chapel-lang.org/docs/usingchapel/multilocale.html).
To set up for Chapel's GPU support, refer to the [GPU Programming](https://chapel-lang.org/docs/technotes/gpu.html) tech note.

## Installing Docker

### Mac

Download the docker desktop for Intel or Arm as appropriate from
https://docs.docker.com/get-docker/.

Start up docker desktop.  You do not need a docker account.


### Linux

* First three steps on https://docs.docker.com/engine/install/ubuntu/
  1. Set up Docker's Apt repository.
      ```
            # Add Docker's official GPG key:
                  sudo apt-get update
                        sudo apt-get install ca-certificates curl gnupg
                              sudo install -m 0755 -d /etc/apt/keyrings
                                    curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
                                          sudo chmod a+r /etc/apt/keyrings/docker.gpg

      # Add the repository to Apt sources:
            echo "deb [arch="$(dpkg --print-architecture)" signed-by=/etc/apt/keyrings/docker.gpg]   https://download.docker.com/linux/ubuntu "$(. /etc/os-release && echo "$VERSION_CODENAME")" stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
                  sudo apt-get update
                      ```

  2. Install the Docker packages.
      ```
            sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
                ```

  3. Verify that the Docker Engine installation is successful by running the hello-world image.
      ```
            sudo docker run hello-world
                ```


* Additional steps
    ```
          sudo groupadd docker
                sudo usermod -aG docker ${USER}

      # maybe not necessary
            sudo chmod 666 /var/run/docker.sock

    ```

### Windows

1. download docker for windows from: https://docs.docker.com/desktop/install/windows-install/
  a. when promted to log in or create an account, select continue without logging in

2. open a Powershell terminal (preferably as admin)
  a. if you don't have WSL installed, execute `wsl --install`
    b. next, ensure that your Ubuntu distro is using WSL2 (rather than WSL1).
      Execute `wsl -l -v` and ensure that ubuntu says 2 under version.
         i. If it is on version 1, execute `wsl --set-version ubuntu 2` (may take some time)

3. open the docker desktop app to start the docker daemon
  a. you can check that docker is using WSL Ubuntu by going to
    Settings > Resources > WSL Integration

4. in Powershell, execute docker pull chapel/chapel-gasnet

*NOTE*: For Windows you will probably have to replace the `$PWD` from the instructions
at https://hub.docker.com/r/chapel/chapel with the Windows version of the current path
written out