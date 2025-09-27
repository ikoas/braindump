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

### Adding Files

In layman terms, Git keeps all it's info inside the `.git` directory, this includes every version of your project's files but they have to be **added** by you. You can do this with the command `git add`, this will take a snapshot of the files you tell it to. For example, imagine the following file structure:

```
./.git/
./batman.txt
./stark.txt
./t-800.txt
```

Right after running `git init` the `.git` directory doesn't have any files inside, so you could consider your repository empty. If you then run `git status` you'll get a message about the current status of your repository. We'll get a message similar to the following if we run `git status` in our example:

```
On branch main

No commits yet

Untracked files:
  (use "git add <file>..." to include in what will be committed)
	batman.txt
	stark.txt
	t-800.txt

nothing added to commit but untracked files present (use "git add" to track)
```

To add a file we just need to specify the file in the command. Let's add `batman.txt` to our repository, to do this we just need to run `git add batman.txt`. Now lets run `git status` and see what happened:

```
On branch main

No commits yet

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)
	new file:   batman.txt

Untracked files:
  (use "git add <file>..." to include in what will be committed)
	stark.txt
	t-800.txt
```

Now `batman.txt` has been added but notice how all other files haven't. For the sake of completeness, what was added was the current version of `batman.txt` not `batman.txt` itself, if we change it, the version added will still be the version of the file that was added when we ran `git add`. Let's see this in action. First let's see what's inside `batman.txt`:

```
I'm Batman
```

Ok, let's change it:

```
I'm Batman
Bitch
```

Let's see what `git status` has to say:

```
On branch main

No commits yet

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)
	new file:   batman.txt

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
	modified:   batman.txt

Untracked files:
  (use "git add <file>..." to include in what will be committed)
	stark.txt
	t-800.txt
```

As you can see the message has a new section. According to Git, `stark.txt` and `t-800.txt` are untracked. What does that mean? It means that these files haven't been added at all. The only file added so far is `batman.txt` but Git shows it has changes to be committed and changes that are not staged for commit. What's that all about? Remember that we said commits are snapshots of our project? Running `git add` adds files and groups them to form a commit, this means that you can pick and chose specific parts of your project to snapshot. Returning to the message `git status` printed, this means that at this moment we added a version of `batman.txt` to our **commit** but we modified the file and those changes are not in the version that is part of our commit. 

Here's a useful command: `git diff`. This command shows you detailed differences. You can use it to show specific differences between commits or between commits and the files outside the `.git` directory. In our example, if we use the command `git diff` we get a message like the following:

```
diff --git a/batman.txt b/batman.txt
index d0943e8..a707705 100644
--- a/batman.txt
+++ b/batman.txt
@@ -1 +1,2 @@
 I'm Batman
+Bitch
```

Running this command on a terminal will use colors that will make understanding the message easier. In this case the message can be summarized like this, there are 2 versions, the first version is the one we added with `git add` and is staged for commit, and the other version is the one we modified, which says:

```
I'm Batman
Bitch
```

**Quick Tip:** You can add all files under your current directory position recursively by running `git add .`. This means that if you are inside a directory on your project, this command will add every file in that directory and every file inside every directory that in there.

### Committing

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