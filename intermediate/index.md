---
layout: curriculum
title: GitHub Intermediate
description: Leveraging Git and GitHub from the command line
---
 

This curriculum will be your companion to the GitHub Intermediate class taught by the GitHub Training Team and other educational groups. In this course, you'll learn how to extensively leverage Git and GitHub from the command line.

![Git repository creation at the command line](../assets/screenshots/terminal-repo-creation.jpg)

### Git Configuration
Git is configured through name-value pairs saved in an [INI file format](http://en.wikipedia.org/wiki/INI_file). The name-value pairs can be read and written through the `git config` command.

Git's configuration is saved in one of three plain text files and one of three levels and is easily editable with a text editor and portable to other machines by copying the configuration files.

#### Identity
Your name and email address are configured locally in Git and are attached to each commit. Set these accurately to receive proper attribution for your work.

These are the very first Git elements often suggested to set. If not set, Git will fall back to an automatically derived name and email from the host machine's network node name.

To inspect the current settings, individually query two configuration values:

```shell
$ git config user.name
Firstname Lastname

$ git config user.email
someaccount@example.com
```

To set the same values to apply to any of your repositories:

```shell
$ git config --global user.name "your name"
$ git config --global user.email "your@email"
```


```shell
$ git config user.name "[your full name]"
$ git config user.email "[youremail@yourdomain.country]"
```

If using the GitHub for Windows or GitHub for Mac GUIs, these values are set, system-wide, by each GUI's configuration dialog.

![GitHub for Mac Advanced Preferences](../assets/screenshots/github-for-mac-advanced-preferences.png)

#### Scopes
Git configuration can be set at one of the three aforementioned levels.  The most common is `global`, and is used for all cross-repo but per-user settings.

Level | Precedence | Location
--- | --- | ---
`system` | lowest | alongside the `git` binary
`global` | middle | in your home directory as `.gitconfig`
`local` | highest | in your project's `.git/config` file

&nbsp;

To use each of the scopes in a setting or getting action of `config`, simple provide the scope's name alongside the config action:

```shell
$ git config --system [name] [value]
$ git config --global [name] [value]
$ git config --local [name] [value]
```

#### Line endings
The line ending setting is one of the most common settings users choose to set early in their use of Git. Some Git configuration options, like this one, affect platform-targeted behavior:

```shell
# Set line endings to LF for Mac and Linux
$ git config --[scope] core.autocrlf input
```

```shell
# Set line endings to CRLF for Windows
$ git config --[scope] core.autocrlf true
```


#### Listing configuration
Listing the current configuration is as easy as asking for the entire set of name-value pairs:

```shell
# List all inherited configuration
$ git config --list
```

```shell
## List all configuration for a given scope
$ git config --list --[scope]
```

Some configuration options have become defaults over time:

```shell
# Enable use of color in output for Git versions older than 1.8.x
$ git config --[scope] color.ui auto
```

#### Video
<iframe src="//player.vimeo.com/video/88276099" width="100%" height="350" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen></iframe>

#### Further reading
* [Pro Git Book: First Time Git Setup](http://git-scm.com/book/en/Getting-Started-First-Time-Git-Setup)
* [Book chapter on Configuring Git](http://git-scm.com/book/en/Customizing-Git-Git-Configuration)
* [Git documentation on the config command](http://git-scm.com/docs/git-config)

##### Lab: Configuration
1. Verify the current value of your username and email address as known by Git.
2. If needed, set your username and email address using the `git config` command.
3. If on Windows, set your line ending behavior to `core.autocrlf true`
4. If on Mac, set your line ending behavior to `core.autocrlf input`
5. List out all your remaining Git configuration values.


### Start a repository
Git provides an easy way to get started versioning any prototype, prose or project with a terse command line recipe.

Initialize a repository and create a top level project directory:

```shell
# For a new project...

$ git init [projectname]
$ cd [projectname]

# ...start coding
```

Initialize a repository inside a top level project directory:

```shell
# For an existing project...

$ cd [existingprojectname]
$ git init

# ...start coding
```

Acquire a project:

```shell
$ git clone [repository-url]
```

```shell
$ git clone [url] [optional-folder-name]
```

#### Video
<iframe src="//player.vimeo.com/video/88313612" width="100%" height="350" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen></iframe>

### Versioning content

```shell
$ git status
```


```shell
$ git add [filename]
```

```shell
$ git commit -m "[your description]"
```

#### Three stage thinking
{% capture svg_path %}../assets/diagrams/commit-three-stage.svg{% endcapture %}
{% include svg %}

#### Commit versions
{% capture svg_path %}../assets/diagrams/commit-versions.svg{% endcapture %}
{% include svg %}

#### Commit DAG
{% capture svg_path %}../assets/diagrams/commit-dag.svg{% endcapture %}
{% include svg %}

#### Video
<iframe src="//player.vimeo.com/video/88315552" width="100%" height="350" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen></iframe>


### Review pending modifications
Git advocates precision in each commit's contents and commit message.  This is facilitated by easy reviewing of in-flight changes prior to describing them and making them permanent.

{% capture svg_path %}../assets/diagrams/diff.svg{% endcapture %}
{% include svg %}

The simplest invocation of `diff` is the most common.  It displays

```shell
$ git diff
```

Git creates a distinction between what is modified and unselected and what has been staged for commit. A well-named `diff` option switch allows for the inspection of each of these two groups of changes.

```shell
$ git diff --staged
```

The default line-level difference indicators are sometimes insufficient for prose and small variable-name changes. An option instructs Git to perform and highlight intra-line comparisons.

```shell
# Highlight word changes on lines
$ git diff --color-words
```

Diff, by default, performs comparisons on all modified files. If inspection of just a subset is called for, `diff` accepts a precise or wildcard-ed filename or path as an option.

```shell
# By specific file
$ git diff [file-path]
```

#### Video
<iframe src="//player.vimeo.com/video/88315553" width="100%" height="350" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen></iframe>


### Review historical changes
Lorem ipsum dolor sit amet, vitae risus eu. Risus pede. Etiam facilisi quis, iaculis cum sed, eu mauris. Magna turpis. Etiam sed voluptatem.

```shell
$ git log
```

Some simple option flag additions to the `log` invocation can make the output more information-dense.

```shell
# Simple commit summaries
$ git log --oneline
```

And if displaying the full contents of the change and word-level comparision are helpful, there are option switches for that too.

```shell
# Option switches common with `diff`
$ git log --patch --color-words
```

#### Video
<iframe src="//player.vimeo.com/video/95811891" width="100%" height="350" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen></iframe>


### Local workflows

Organizing history:

{% capture svg_path %}../assets/diagrams/what-is-a-branch.svg{% endcapture %}
{% include svg %}


#### Branching
Git branch:

```shell
# List branches, identify current brach
$ git branch

# Create a new branch from current branch
$ git branch [name]

# Switch to a different branch
$ git checkout [name]
```

Option switches:

```shell
# Rename any branch
$ git branch -m [current-name] [new-name]

# Delete a *reachable* branch
$ git branch -d [name]

# Delete whether or not reachable
$ git branch -D [name]
```

#### Checkout video
<iframe src="//player.vimeo.com/video/100127088" width="100%" height="350" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen></iframe>

#### Branching video
<iframe src="//player.vimeo.com/video/100128962" width="100%" height="350" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen></iframe>

Git merge:

```shell
# Integrate history of specified branch into current one
$ git merge [branch]
```

Merge fast-forward:

{% capture svg_path %}../assets/diagrams/merge-fast-forward.svg{% endcapture %}
{% include svg %}

Merge recursive:

{% capture svg_path %}../assets/diagrams/merge-recursive.svg{% endcapture %}
{% include svg %}


### Distributed repositories

{% capture svg_path %}../assets/diagrams/distributed-version-control.svg{% endcapture %}
{% include svg %}

Git is capable of working with 0 to N remotes. 0 means the local repo only knows about the local file system, 1 represents a more traditional centralized model, and 1+N is an example of the "distributed" multi-mastered facet of a DVCS.

```shell
# List remote "bookmarks", if any
$ git remote
```

Additional remotes (bookmarks) are added as a name-URL-value pair. The default name, as established by a `clone` operation, is `origin`. Another common remote name is `upstream`, seen most frequently in Fork-and-Pull workflows.

```shell
# Add a remote "bookmark"
$ git remote add [name] [url]
```


### Remote workflows

{% capture svg_path %}../assets/diagrams/fork-structure.svg{% endcapture %}
{% include svg %}

Acquiring a repo:

```shell
$ git clone [repository-url]
```

#### Retrieval behavior configuration

Adjusting the `pull` to rebase any local changes on top of inbound ones from the upstream branch:

```shell
$ git config --[scope] pull.rebase true
```

Retrieving branch changes in discrete steps:

```shell
# Retrieve all remote branches, then list them
$ git fetch
$ git branch -a
```


#### Retrieving changes

If retrieval and incorporation are desired to happen in one action, `pull` is the appropriate command:

```shell
# Retrieve remote history and update working tree
$ git pull
```

If the goal is branch retrieval prior to disconnecting from a network, preserving the changes for later review and incorporation, use `fetch`:

```shell
# Only retrieve remote history
$ git fetch

$ git branch -r
```

Git also facilitates ad-hoc branch retrieval to `FETCH_HEAD` with or without a remote:

```shell
# Temporarily retrieve a repository's branch from a remote
$ git fetch [remote] [branch]
```

```shell
# Temporarily retrieve a repository's branch from a URL
$ git fetch [url] [branch]
```

#### Sharing changes

{% capture svg_path %}../assets/diagrams/network.svg{% endcapture %}
{% include svg %}

A fully-specified push can indicate both the destination and contents:

```shell
# Send branch's commit to specific remote
$ git push [remote] [branch]
```

If a push pattern for a given branch will be used frequently, `-u` instructs Git to remember the remote and branch association.

```shell
# Setup and publish branch's commits
$ git push -u [remote] [branch]
```

The most simplistic invocation of `push` leverages _tracking_ as set up by a `clone` or `push -u` to suggest which branches to transmit:

```shell
# Send any local commits to the tracking upstream branch
$ git push
```


### Shortcuts and custom commands

```shell
# Shortcut to output commit history
$ git config --global alias.l "log --oneline --stat"
```

```shell
# Quick graph of commit history and branches
$ git config --global alias.lol "log --graph --all --oneline --decorate"
```

```shell
# Shortuct to repository status
$ git config alias.s "status -s"
```


### File lifecycle
Files in Git transition through a well-defined states of tracking.

{% capture svg_path %}../assets/diagrams/states-of-tracking.svg{% endcapture %}
{% include svg %}

#### Adding files

```shell
# Stage all updated files
$ git add -u [file|pattern]
```

```
# Stage all files no matter the state
$ git add -A [file|pattern]
```

#### Removing files

When already tracked files are no longer needed, they can be removed from tracking and from the file system:

```shell
# Permanently delete file, stage for commit
$ git rm [file]
```

If there's a reason to preserve the file on disk after removing it from tracking, Git facilitates this behavior variant:

```shell
# Stop version tracking, stage for commit
$ git rm --cached [file]
```

#### Remove video
<iframe src="//player.vimeo.com/video/97444896" width="100%" height="350" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen></iframe>

#### Moving files

```shell
# Change the path of a file
$ git mv [path]
```

#### Reviewing moved files

```shell
# Show history including those with prior path names
$ git log --stat -M
```

#### Move video
<iframe src="//player.vimeo.com/video/98954619" width="100%" height="350" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen></iframe>

#### File similarity video
<iframe src="//player.vimeo.com/video/99213354" width="100%" height="350" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen></iframe>

### Undoing changes

#### Revert
Revert is the kindest of undo functionality. It creates a new _inverse_ commit and links back to the old one in the proposed commit message:

```shell
# Create a new commit undoing the patch in that specified
$ git revert [commit]
```

#### Reset

```shell
# Move current branch's HEAD to point in history
$ git reset [commit|branch|tag]
```

Reset offers a plethora of options to adjust the nuances of its restorative behavior:

```shell
# Move HEAD, keep changes in staging
$ git reset --soft [commit|branch|tag]

# Move HEAD, keep changes, clear staging area
$ git reset --mixed [commit|branch|tag]

## Move HEAD, discard all uncommited changes
$ git reset --hard [commit|branch|tag]
```

### Recovering anything

#### Reviewing historical states

```shell
$ git reflog
```

#### Restoring a historical state

```shell
$ git reset --[option] HEAD@{[n]}
```

#### Specific paths

```shell
$ git checkout HEAD@{[n]} -- [path]
```
