<!-- *   git remote add (9,900): this command actually doesn't have anything to do with `git add`, but rather with working with remotes. This should probably be its own page in the future -->

# Git Add

The `git add` command adds new or changed files in your working directory to the Git staging area.

`git add` is an important command - without it, no `git commit` would ever do anything. Sometimes, `git add` can have a reputation for being an unnecessary step in development. But in reality, `git add` is an important and powerful tool that allows you to shape history intentionally without changing how you work.

![image of working directory, staging area, and committed history with commands shown and visualized]()

<!--*   Spiderweb menu of related terms here. -->

## When do you use `git add`?

As you're working, you change and save a file, or multiple files. Then, before you commit, you must `git add`. This step allows you to choose what you are going to commit. Commits should be logical, atomic units of change - but not everyone works that way. If you are making changes to files that _aren't_ logical or atomic units of change, `git add` allows you to systematically shape your commits and your history.

### What Does Git Add Do?

`git add [filename]` selects that file, and moves it to the staging area, marking it as something to be included in the next commit. You can select all files, a directory, specific files, or even specific parts of a file to be staged and committed.

This means if you `git add` a file that has been deleted, the _deletion_ is staged for commit. The language of "add" when you're really "deleting" can be confusing - but if you think or use `git stage` in place of `git add`, the reality of what is happening may be more clear.

`git add` and `git commit` go together hand in hand - they don't work when they aren't used together, and they both work best when used thinking of their joint functionality.

## How to Use `git add`

### Common usages and options for `git add`

*   `git add <path>`: Stage a specific directory or file
*   `git add .`: Stage all files (that are not listed in the `.gitignore`) in the entire repository
*   `git add -p`: Interactively stage hunks of changes

You can see all of the many options with `git add` in [git-scm's documentation](https://git-scm.com/docs/git-add).

## Examples of `git add`

`git add` usually fits into the workflow in the following steps:

1. Create a branch
2. Checkout to that branch
3. Change a file or files
4. Save the file or files
5. Add the files or segments of code that should be included in the next commit
6. Commit the changes
7. Push the changes to the remote branch

But, `git add` could also be used like:

1. Create a branch
2. Checkout to that branch
3. Change a file or files
4. Save the file or files
5. Add only one file, or one part of the changed file
6. Commit the first set of changes
7. Add another file, or another part of the changed file
8. Commit the second set of changes
9. (Repeat as necessary)
10. Push the changes to the remote branch

### `git add` All Files

Staging all available files is a popular, though risky, operation. This can save time, but the risks are two-fold:

#### Poorly thought out history

By habitually staging all available changes, the clarity of your history will likely suffer. Being able to shape your history is one of the greatest advantages of using Git - and if your commits are too large, contain unrelated changes, or are unclearly described in the commit message, you will lose the benefits of being able to quickly peruse or change history.

#### Accidentally staging and committing files

By using an option to add all files at once, you may accidentally stage and commit a file. Though most common flags don't add files tracked in the `.gitignore` file, any file that hasn't yet been documented there is at risk of being staged and committed. This applies to large binary files, or files containing sensitive information like passwords or authentication tokens.

#### Deciding to stage all files

If and when the time is right to stage all files, there are several commands that you can choose from. They do slightly different things, and as always, it's very important to know what you are staging and committing.

*   `git add -A`: stages all files, including new, modified, and deleted files, including files in the current directory _and_ in higher directories that still belong to the same git repository
*   `git add .`: adds the entire directory recursively, including files whose names begin with a dot
*   `git add -u`: stages new and modified files only, NOT deleted files

| | New files | Modified files | Deleted files | Files with names beginning with a dot | Current directory | Higher directories|
| ------------- | ------------- | ---- | ---- | ------ | ----- | ----- |
| `git add -A ` | Yes | Yes | Yes | Yes | Yes | Yes |
| `git add .` | Yes | Yes | Yes | Yes | Yes | No |
| `git add -u` | No | Yes | Yes | Yes | Yes | Yes |

### `git add` A Folder or Specific File

The safest and most highly recommended way to use `git add` is by designating the specific file or directory to be staged. The syntax for this could look like:

`git add directory/`: Stage all changes to all files within a directory titled `directory`
`git add README.md`: Stage all changes within the `README.md` file

### Undo Added Files

Before undoing a `git add`, you should first be sure that you won't lose any work. There's no way to "revert" an add in the same way you can revert a commit, but you can move the files out of the staging area. 

An example of how you might lose work would be if you have a staged file, and then you make more changes to that file in your working directory. Now, the versions in your working directory and your staging area are different. If you take action to remove the changed version of the file from the staging area, the changes that were in your working directory _but not_ staged will be overwritten.

To avoid this, first stage all changes, then unstage them together, or commit the changes and reset back before the commit happened.

#### Using `git reset` to undo `git add`

`git reset` is a flexible and powerful command. One of its many use cases is to move changes _out_ of the staging area. To do this, use the "mixed" level of reset, which is the default.

To move staged changes from the staging area to the working directory without affecting committed history, first make sure that you don't have any additional changes to the files in question as mentioned above. Then, type `git reset HEAD` (aka `git reset --mixed HEAD`).

## Related Terms

- `git status`: Always a good idea, this command shows you what branch you're on, what files are in the working or staging directory, and any other important information.
- `git checkout [branch-name]`: Switches to the specified branch and updates the working directory.
- `git commit -m "descriptive message"`: Records file snapshots permanently in version history.
- `git push`: Uploads all local branch commits to the remote.
  