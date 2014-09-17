# git-update

A dead simple git command that tries to just get the latest version without drama.

# Installation 
Here's one way to do it:

    git clone https://github.com/itsadok/git-update
    cd git-update
    git config --global alias.update "!$(pwd)/git-update"

# Usage

Just run `git update` in a git repository. The command will do the following:

1. Fetch from default remote.
2. Try to do a ff merge.
3. If that fails, try to rebase over remote branch.
4. If there are conflicts, try to merge with remote branch.
5. If there are conflicts, show an error message and restore the repository to its original condition.

The stash will be used, so you don't have to do this on a clean repository. If the stash won't apply cleanly, 
the repository will be restored to its original condition.

# To do

* Add options to use non-default remote and refspec.
* Do a smart pull, like legit does it (don't rebase if there are merges in local branch).
* http://stackoverflow.com/questions/15316601/why-is-git-pull-considered-harmful
* https://gist.github.com/Boldewyn/8454951

# Author

Israel Tsadok. Code license - [CC0](http://creativecommons.org/publicdomain/zero/1.0/).

