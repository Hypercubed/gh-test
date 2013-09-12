gh-pages content from master
===


# Setup

Create your master branch:

    $ cd project && cd project
    $ git init

Create your files and commit:

    $ git add .
    $ git commit -m "First commit"

Now create gh-pages branch

    git checkout --orphan gh-pages
    git read-tree --prefix=_includes/ -u master
    git commit -m "Master merged into gh-pages as subtree"

# Maintenance

Work on your master branch as normal.  Commit changes.  When ready to push:

    git checkout gh-pages
    git merge -s subtree master --commit
    git checkout master

Finally push

    git push --all origin
