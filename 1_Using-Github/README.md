# Topic 1
## Using GitHub

GitHub is an absolutely essential tool in the arsenal of modern astronomers (and almost every other tech-focused career). It is an online version control manager, which can interface with `git` version control on your own machine. Using `git`, when you save work to a so-called 'repository', you can save whatever version you're currently working on, and always revert to past versions if you want to. Using GitHub, you can then upload these files, where they'll be stored and accessible from any machine anywhere.

GitHub is also important for collaboration. You can create 'branches', where you can work on a new addition to some code until you're happy with it, and then 'merging' it back into the main repository. Or you can create a 'fork' -- a personal copy of a repository -- to make changes you want, before making a 'pull request' to merge your changes back into the main repository, in a process that allows your colleagues to weigh in and make changes themselves (for this, see *Topic 3*).

To access GitHub, you use `git` commands in the commandline on your computer. However first, set up your account! This will let you upload (push) changes you make to this repository for everybody to see. There's a [GitHub Cheat Sheet](https://github.com/ojhall94/LEAPS2021/blob/main/git-cheat-sheet.pdf) on the repository for further tips and tricks!

### Cloning a repository
Navigate to the directory on your computer where you want to place the repository, and type the following into commandline:

```bash
git clone https://github.com/ojhall94/LEAPS2021_workshop.git
```

This has created a clone of the GitHub repository on your computer.

### Branches

Sometimes we want to make a major change to some code that already works well, and don't want to risk losing our progress. This is a great opportunity to use *branches*. A branch is a copy of the repository with a new commit history starting from the point at which you create the branch. Branches can stay separate the way they are, or eventually be *merged* back into the `main` branch when you're satisfied with your changes. We do this using the process of a *pull request*, which checks that your changes are compatible with the `main` branch.

It's easier to show this in practice. First, let's create a new branch.

```
git branch <your name>
git checkout <your name>
git branch
```

Where <your name> can be anything you want, so long as its unique to you (somehow!)
I chose the name "leaps", so I'll see a list that looks something like this:

```
main
* leaps
```

This tells you that you are now on the "leaps" branch.

### Making a git commit
First, lets make a commit to your branch. Open `HELLO.md` on your computer, and add something that marks you've been here! Like your name, a favourite quote, or perhaps a fun .gif. For tips on markdown syntax, look here: https://guides.github.com/features/mastering-markdown/

Now save and close the file, and go back to your commandline. By typing

```bash
git status
```

you can see that `HELLO.md` has been updated. You can see these exact changes by using `git diff`.

We can save this version of the document by making a commit. We add a message to the commit, so we know what we did. First, we need to add the file to the commit.

```bash
git add HELLO.md
git commit -m "Added some text to the HELLO file"
```

This permanently stores this updated version of the repository! Finally, we can make sure that this commit is also backed up online, by 'pushing' to GitHub.

```
git push
```

*Tip*: You can add all files to the commit using `git add .`, but be careful! You want to make sure you don't include large data files or presentations that might be too big for GitHubs storage space.

*Tip*: You'll see there's a `.gitignore` file in the repository. This lists all the file types that are automatically never committed. If you have any large files you don't want to upload (but do want to store in this repository), add their names to the `.gitignore`.

### Merging via Pull Request

When you made your commit earlier, you made it to the <your name> branch! You can see that this is the case by moving back to the main branch and checking the file.

```
git log
git checkout main
git log
```

You'll see that the `git log`, which shows the commit history for the branch, is different for the `main` and `<your name>` branches! You can navigate back using `git checkout <your name>`.

Now that you've made your changes, you'll want to push these changes to GitHub.  Since the branch you made (hopefully) doesn't exist, you have to use the following command:

```
git push --set-upstream origin <your name>
```

but if the branch already exists on GitHub then you only need to use `git push`.

Finally, once you're happy with your changes you can *merge* the branch back into `main`! You do this using a Pull Request. You can [open a new Pull Request on the repository here](https://github.com/ojhall94/LEAPS2021_workshop/compare). You can pick the branches to merge, and GitHub will check automatically for you whether there are any clashes. Since I am the owner of the repository, I will need to approve the Pull Request! Once I've done so, the contents of your branch, along with the branch's entire commit history, will become part of `main`.

*Tip*: When working on a branch you plan to eventually merge back into `main`, it is *really* important that you don't also work on the same file in `main` at the same time! When GitHub compares the two branches in a pull request, it will see that the two files clash with one another, and might not be able to merge them. Resolving this (usually) requires manually going through and picking and choosing which lines of code to keep... best to avoid it! I realise this is hypocritical, because everybody will be editing the same file... but hopefully the changes will be simple enough that it won't make a difference :)

### Pulling
GitHub backs up your repository (provided you've `git push`ed!), and so you can access it from anywhere! In order to sync up your computer with the state of the GitHub repository, you *pull* the changes using:

```
git pull
```

It's always a good idea to `git pull` before you get started with work, in case somebody has added to the repository (or you have from a different machine). Maybe wait 5 minutes and `git pull` the `main` repository branch again. Somebody might have added a new .gif to the `HELLO.md` file!
