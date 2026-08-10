git reset

By itself, git reset means:

git reset HEAD

It does not move HEAD to another commit.

It simply unstages your staged changes.

Example:

Working directory
       ↓
    Staging area
       ↓
     HEAD

Suppose you do:

git add file.txt

Now the file is staged.

Then:

git reset

moves it out of staging, but keeps your file changes.

Before:

Working → Staging → HEAD
           file.txt


git reset

Working → HEAD
file.txt is now unstaged

So:

git reset

= unstage everything

git reset --hard

By itself:

git reset --hard

means:

git reset --hard HEAD

It resets both:

Staging area
Working directory

to match HEAD.

So if you have modified a file:

HEAD:
hello

Working directory:
hello world

Run:

git reset --hard

and:

Working directory:
hello

Your modification is discarded.

Simple difference
git reset
       ↓
Unstage changes
Keep file changes


git reset --hard
       ↓
Unstage changes
DISCARD file changes

That's the distinction when no commit/ref is specified.