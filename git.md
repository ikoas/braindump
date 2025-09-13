---
aliases:
  - Git
---

[Wikipedia](https://en.wikipedia.org/wiki/Git) describes Git as follows:

> **Git** ([/ɡɪt/](https://en.wikipedia.org/wiki/Help:IPA/English "Help:IPA/English") [🔊](https://upload.wikimedia.org/wikipedia/commons/transcoded/9/9a/En-uk-git.ogg/En-uk-git.ogg.mp3 "Play audio")[ⓘ](https://en.wikipedia.org/wiki/File:En-uk-git.ogg "File:En-uk-git.ogg")[\[8\]](https://en.wikipedia.org/wiki/Git#cite_note-:0-9)) is a [distributed version control](https://en.wikipedia.org/wiki/Distributed_version_control "Distributed version control") [system](https://en.wikipedia.org/wiki/Software_system "Software system")[\[9\]](https://en.wikipedia.org/wiki/Git#cite_note-FOOTNOTEChaconStraub201429%E2%80%9331-10) that tracks versions of [files](https://en.wikipedia.org/wiki/Computer_file "Computer file"). It is often used to control [source code](https://en.wikipedia.org/wiki/Source_code "Source code") by [programmers](https://en.wikipedia.org/wiki/Programmer "Programmer") who are [developing](https://en.wikipedia.org/wiki/Software_development "Software development") software collaboratively.

You can learn more about Git here:
- Git's official Website: https://git-scm.com/about
- Learn X in Y minutes' page on Git: https://learnxinyminutes.com/git/
- arslanbilal's Git cheat sheet: https://github.com/arslanbilal/git-cheat-sheet
- Oh My Git! - An open source game about learning Git!: https://ohmygit.org/

# ELI5; What is Git?

Git was built as a way to help teams deal with multiple changing files on a project and maintaining a timeline of different changes and versions of a project.

You could kind of think of Git as save files in video games. As save files in video games, Git lets you save your progress on a project and even go back to previous save files.

# ELI5; Basic Git Concepts

While using Git you'll find many words that at first may not make any sense. I'll try to explain some of the more commonly used words.

- **Repository / Repo**: You can think of a repository as the container for the files that make up your project.
- **Commit**: Keeping inline with the video game analogy, you can think of a commit like a save file. Basically it takes a snapshot of your project.
- **Branch**: You can think of a branch kinda like an alternate version of your project. Going back to the video game analogy, its like when you keep two separate save files where you make different choices, kinda like having a save file for playing like a law-abiding citizen and another where you are a super villain wrecking everything in its path. 
- **Merge**: This is an operation that tries to merge two branches into a single branch. Returning to the video game example, you could imagine it like taking two different save files and trying to get a save file that has the progress, changes and decisions of both.

# Basics of Using Git

Git, as a tool, is designed to be used on a terminal. There are other tools that provide a graphical interface to use Git, but this section with focus on using Git by itself, using a terminal, so some knowledge about using a terminal is expected.

## Creating a Repo

Creating a repo is as simple as running the command `git init`. This will establish the current location as a repo, and will create a directory called `.git` where all the info describing the repo and data required for Git to work will be saved.

Is important to note that every directory outside the current location is not part of the repo, so every file of your project that you wish to be included inside the repo should be inside this location.

---

The following sections expect you to be inside a git repo in order to work. Any directory inside the repo, except inside the `.git` directory, will work.

## Basic Configurations

Git is designed to be used by teams. There is nothing stopping you from using it alone as an individual, but because of this, Git expects some info about the user in order to assign authors to changes in the project. At a minimum, Git expects a name and an email.

You can set up your name by using the command `git config user.name "Your Name"`, and your email with `git config user.email "Your Email"`. This will only set up this info for only this repo, if you want to set this info for your system user, you can add the `--global` flag, like so `git config --global user.name "Your Name"`. You can also user the `--system` flag to set up this info for the whole system.

**Note:** You can put whatever you want under name and email but it is recommended that you don't set up empty fields or enter invalid email addresses.

## Tracking Changes

#TODO Working Tree and Index. How does `git add`, `git commit` and `git restore`? Supporting commands `git status`, `git diff`, `git log` and `git tag`.

---

#TODO

Subjects:
- Remotes
- Upstream
- Commit
- Repo
- Branches
- push
- pull
- fetch
- checkout
- atomic commits