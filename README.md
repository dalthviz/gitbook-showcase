# Gitbook Template

> A Gitbook seed project

## What is this ?

This is a template project for creating books using Gitbook.

## What is the software required to install it ?

You must have installed [node.js](https://nodejs.org), [Git]((https://git-scm.com/downloads)) and the [Gitbook Commando Line tools](https://github.com/GitbookIO/gitbook-cli)

- For node.js
  - To check if the node.js is installed, you may execute:
    ```
    $ npm -v
    ```
  - if it is not installed, you must download and install the software from [the official node.js website](https://nodejs.org/en/download/)

- For Git
  - To check if Git is installed, you may execute:
    ```
    $ git --version
    ```
  - if it is not installed, you must download and install the software from [the official Git website](https://git-scm.com/downloads)

- For Gitbook Cligitbook
  - To check if Gitbook-Cli is installed, you may execute:
  - If it is not installed, you must install the package using npm as an administrator
    ```
    $ npm install -g gitbook-cli
    ```
  - In linux or mac, you may use ``sudo``to set the user for the ``.npm`` folder and install the package
    ```
    $ export PATH=$PATH:$HOME/.npm-packages/bin
    $ sudo chown -R $USER:$GROUP ~/.npm
    $ sudo npm install -g gitbook-cli
    ```


## How to install it ?

To deploy the book in a Github-Pages website, you must change the URL for the repository in the ``package.json`` file.

- Check the name of the repository in the Github.
- Replace the name of the repository. By default, it is "noname/noname.git"

## How to run it ?

The project includes a set of commands that can be used to automate part of the process.

- To install or update the Github plugins, if required.

  ```
  $ npm book:prepare
  ```

- To preview the book. It runs a webserver where you can review the book while you are writing. Any change in the book is displayed immediately.

  ```
  $ npm book:watch
  ```

- To create the book (in Windows)

  ```
  $ npm book:build
  ```

- To publish the book in a Github-Pages website (in Windows)

  ```
  $ npm book:publish
  ```

- To create the book (in Linux)

  ```
  $ npm book:build-linux
  ```

- To publish the book in a Github-Pages website (in Linux)

  ```
  $ npm book:publish-linux
  ```

