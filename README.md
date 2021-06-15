# akshay
echo "# akshay" >> README.md
git init
git add README.md
git commit -m "first commit"
git branch -M main
git remote add origin https://github.com/Akshay19040/akshay.git
git push -u origin main
echo "# akshay" >> README.md












git push -u origin main
echo "# akshay" >> README.md

git init

git add README.md

git commit -m "first commit"

git branch -M main

git remote add origin https://github.com/Akshay19040/akshay.git

git push -u origin main

Signed-off-by: Andrei Jiroh Eugenio Halili <andreijiroh@madebythepins.tk>

* [gitpod] Update README for some Gitpod stuff + Add Gitpod config and Dockerfile

Signed-off-by: Andrei Jiroh Eugenio Halili <andreijiroh@madebythepins.tk>

* [flask] Use port 8080 if PORT variable is undefined due to root access issues

Signed-off-by: Andrei Jiroh Eugenio Halili <andreijiroh@madebythepins.tk>

* [gitpod] Update config file for some ports

* [deepsource] Fix styling issues as per https://kutt.it/W6RuVz

Signed-off-by: Andrei Jiroh Eugenio Halili <andreijiroh@madebythepins.tk>

* [gitpod] Gonna rekt due to some errors during image build time

Signed-off-by: Andrei Jiroh Eugenio Halili <andreijiroh@madebythepins.tk>

* [heroku] v7 gone brrrrrrrrr

 master (#5)

@AndreiJirohHaliliDev2006

AndreiJirohHaliliDev2006 committed on 19 Jun 2020 

1 parent 2820a82 commit 850d9a75e49de867482b731b0bd05b79f117c499

Showing  with 40 additions and 7 deletions.

  3  .gitignore 

@@ -123,3 +123,6 @@ dmypy.json

# Pyre type checker

.pyre/

# Swap files on using Vi or Vim

*.swp

 9  .gitpod.Dockerfile 

@@ -0,0 +1,9 @@

FROM gitpod/workspace-full

USER gitpod

## Update our system deps

RUN apt-get update && apt-get -y

## Then install Heroku CLI

RUN curl https://cli-assets.heroku.com/install.sh | sh

 12  .gitpod.yml 

@@ -0,0 +1,12 @@

image:

  file: .gitpod.Dockerfile

# List the ports you want to expose and what to do when they are served. See https://www.gitpod.io/docs/config-ports/

ports:

  - port: 8080

    onOpen: notify

# List the start up tasks. You can start them in parallel in multiple terminals. See https://www.gitpod.io/docs/config-start-tasks/

tasks:

  - init: pip3 install -r requirements.txt

    command: python3 GitGram.py

  3  GitGram.py 

@@ -277,5 +277,6 @@ def deldog(data):

if __name__ == "__main__":

    port = int(environ.get("PORT", 80))

    # We can't use port 80 due to the root access requirement.

    port = int(environ.get("PORT", 8080))

    server.run(host="0.0.0.0", port=port)

 18  README.md 

@@ -1,11 +1,19 @@

[![Gitpod ready-to-code](https://img.shields.io/badge/Gitpod-ready--to--code-blue?logo=gitpod)](https://gitpod.io/#https://github.com/pokurt/GitGram)

# GitGram - Github Integration for Telegram Bot API

# Setup:

## Setup:

- Install all requirements, `pip3 install -r requirements.txt`

- Fill your tokens in `config.py`

- Copy `config.sample.py`, edit and save as `config.py`

- Run `python3 GitGram.py`

# Deploy on Heroku:

One-Click Deploy on Heroku Using Button Down Below:

## Deploy on Heroku:

If you want to deploy this app on Heroku, there's a one-click setup for that. Click below, fill up the form and hit **Deploy App**.

[![Deploy](https://www.herokucdn.com/deploy/button.svg)](https://heroku.com/deploy?template=https://github.com/pokurt/GitGram)

[![Deploy](https://www.herokucdn.com/deploy/button.svg)](https://heroku.com/deploy?template=https://github.com/pokurt/GitGram)

## Try on Gitpod:

1. [Login to Gitpod](https://gitpod.io/login).

2. [Open this repo in Gitpod](https://gitpod.io/#github.com/pokurt/GitGram).

3. After workspace build, dependencies will be installed.

4. Follow step 2 and 3 in Setup section
