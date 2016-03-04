# Tuura test repo

Edit this paragraph to submit a Pull Request.

### Cheatsheet

#### Git basics

To install Git:

https://git-scm.com/book/en/v2/Getting-Started-Installing-Git

For reference and further reading, see:

https://git-scm.com/book/en/v2/Getting-Started-Git-Basics

The rest of the book is an excellent read too.

#### Git/Github setup

Put this in your `~/.gitconfig`:

	[user]
		name = Name Surname
		email = email@domain.com
		editor = vim
	[color]
		ui = true
	[push]
		default = current

More info here: https://git-scm.com/book/en/v2/Getting-Started-First-Time-Git-Setup

Set up your ssh key on Github:

	https://github.com/settings/ssh

Bonus points if you set up two-factor authentication:

	https://github.com/settings/security

#### Forking

Note that these instructions can be applied to `tuura/workcraft` simply
by replacing `mvdan/tuura-testrepo`.

Fork this repo:

	https://github.com/mvdan/tuura-testrepo

Clone your fork:

	git clone git@github.com:username/tuura-testrepo

Look at your remotes:

	cd tuura-testrepo
	git remote -v

Add the original repo as a remote, e.g. `upstream`:

	git remote add upstream https://github.com/mvdan/tuura-testrepo

Set up master to follow `upstream` - this will help you keep your master
up to date:

	git fetch upstream
	git branch --set-upstream-to=upstream/master

#### Submitting your first PR

Make sure you're on `master`:

	git checkout master

Pull from `upstream`:

	git pull upstream

Since we set `master` to track `upstream/master`, you can just do:

	git pull

It is useful to always do your changes in a branch other than `master`.
This way, `master` is always what the upstream repo has.

Create a new branch for your changes:

	git checkout -b my-branch

Run `git status` to see that there are no changes:

	git status

Do your changes, e.g:

	echo "foo" >> README.md

Run `git status` again, and check that `README.md` shows as modified:

	git status

You can also see the changes in a diff:

	git diff

Commit the changes (will open your editor):

	git commit -a

The format for commit messages is as follows:

	Summary (50 characters max)

	Optional long description. You can use multiple paragraphs. Make
	sure to leave an empty line to mark the separation between the
	summary and the description.

	Wrapping the description to 72 or 80 columns is also usual, to
	keep things readable in the terminal interface.

Push the changes to your fork (`-u` makes it track `origin`):

	git push -u origin

Visit the web interface again to open the Pull Request:

	https://github.com/mvdan/tuura-testrepo

After you specify the title of the Pull Request and create it, it should
show up here:

	https://github.com/mvdan/tuura-testrepo/pulls
