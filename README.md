# BI MAGic Model <!-- omit in toc -->

- [1. Introduction](#1-introduction)
- [2. Production Cycle](#2-production-cycle)
- [3. Model Progression](#3-model-progression)
  - [3.1. Development Workflow](#31-development-workflow)
  - [3.2. Making a New Release](#32-making-a-new-release)
- [4. Local Setup](#4-local-setup)


## 1. Introduction

This is a test project within the Wiklander family relating to coding, assembly language, really fun and inspiring old 8-bit computer
And probably a lot more too!

## 2. Production Cycle

Get an idea
Have fun
Push a change if you believe it will benefit humanity

## 3. Model Progression

To keep operations smooth, the preferred workflow is showed in the image below and further described in [3.1. Development Workflow](#31-development-workflow) and [3.2. Making a New Relese](#32-making-a-new-release).

![](assets/git_workflow.png)

### 3.1. Development Workflow

When changes to any work are to be made, the following workflow is preferred.

1. Pull the latest changes from the `dev` branch. 
   
    ```sh
    $ git pull origin dev
    ```
2. Checkout a new branch:
  
      ```sh
      $ git checkout -b <name of branch>
      ```

3. Install a cimpiler
   1. On Mac: $brew install dasm
   2. In Windows: ???

4. Make changes. To have the smoothest experience, here are a few tips.
   1. In order to check your own work run 
  
      ```sh
      $ dasm file.a65 (which will create a new binary: file.out)
      ```
      
      ```in the VICE terminal
      l "file.o" 0 (to load the binary)
      ```
      
      ```in VICE
      SYS $XXXX (where XXXX comes from the first ORG statement in your code)
      ```

    If lots of sprites are flying over your screen, the rasten knocks you out of your chair and the music floating out of the speakers gives you goose bumps
    The you probably did a good job!

   
5. When satisfied, add, commit and push your changes
    ```sh
    $ git add <name_of_file>
    $ git commit -m "adding new exciting model X"
    $ git push --set-upstream origin <name_of_branch>
    ```
6. Create a pull request on GitHub and merge to `dev` branch



### 3.2. Making a New Release

Since we aim at always having the production environment of the model in a stable state, it is important to make sure the development environment is in a stable state before merging with production.

When ready for release, perform the the following steps.

1. Create a PR from `dev` to `main` on GitHub.
2. To minimize errors, assign at least one reviewer.
3. When the review is done, complete the merge.
4. Create a new release in the `main` branch on GitHub. This feature makes it easy to both have an overview of releases and to generate a changelog.
   1. Click *Relases* --> *Draft a new release*.
   2. Set the new tag to the appropriate version, like 1.1 or 2.0.
   3. Set a release title.
   4. Click *Generate release notes* to have GitHub generate release notes based on the PRs in the `dev` branch. The release notes will later be a part of the changelog.
   5. Modify the release notes, since the generated ones might not capture everything.
   6. Click *Publish release*.
5. Notify important stakeholders that a new release is out!

## 4. Local Setup


1. Clone this repo by opening the terminal and navigate to the home folder (or where you prefer) and run 
   
      ```
      $ git clone git@github.com:MAGInteractive-AB/bi-magic.git
      ```

2. Change directory to the bi-magic folder
  
    ```sh
    $ cd bi-magic
    ```

