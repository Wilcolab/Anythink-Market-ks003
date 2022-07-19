# Welcome to the Anythink Market repo

To start the app use Docker. It will start both frontend and backend, including all the relevant dependencies, and the db.

Please find more info about each part in the relevant Readme file ([frontend](frontend/readme.md) and [backend](backend/README.md)).

## Development

When implementing a new feature or fixing a bug, please create a new pull request against `main` from a feature/bug branch and add `@vanessa-cooper` as reviewer.

## First setup

First, follow the link to download Docker Desktop for your OS:
https://docs.docker.com/get-docker/

**Install Docker Desktop on Linux - ubuntu - Gnome environment** 

<b>0) If necessary, uninstall previous docker installation, run:</b>
    
<code>$ sudo apt remove docker-desktop</code>
    
    For a thorough clean up, run:
    
<code>
     $ rm -r $HOME/.docker/desktop
     $ sudo rm /usr/local/bin/com.docker.cli
     $ sudo apt purge docker-desktop
</code>

<b>1) Set up the repository</b>

    1.1) Update the apt package index and install packages to allow apt to use a repository over HTTPS:
<code>
        $ sudo apt-get update
        $ sudo apt-get install \
        ca-certificates \
        curl \
        gnupg \
        lsb-release
</code>
        
    1.2) Add Docker’s official GPG key:
<code>
        $ sudo mkdir -p /etc/apt/keyrings
        $ curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
</code>
    1.3) Use the following command to set up the repository:
<code>
        $ echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \
  $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

</code>


<b>2) Install Docker Engine</b>

    2.1) Update the apt package index, and install the latest version of Docker Engine, containerd, and Docker Compose, or go to the next step to install a specific version:
<code>
        $ sudo apt-get update
        $ sudo apt-get install docker-ce docker-ce-cli containerd.io docker-compose-plugin
</code>

    2.2) Verify that Docker Engine is installed correctly by running the hello-world image.

<code>
        $ sudo docker run hello-world

</code>

<b>3) Install the package with apt as follows:</b>
    Locate your downloaded docker version and run:

<code>
        $ sudo apt-get update
        $ sudo apt-get install ./docker-desktop-<version>-<arch>.deb
</code>

<b>4) Install docker-compose

<code>
        $ sudo apt install docker-compose

</code>

<b>5) Verify Docker is ready by running the following commands in your terminal: </b>

<code>
        $ docker -v
        $ docker-compose -v
</code>

<b>6) Run scripts by running this command in the root of the project</b>
<code>
        $ sudo docker-compose up

</code>