# myrepos, a tool to manage all your version control repos

This is a fork that tries to adhere to the XDG base dir specification for a
better home™.

I'm maintaining this as a method for having a dotfiles repo that has a neat and
low impact on your $HOME without using silly things like symlinking.

In the same vein, as the general usage is done in tandem with
[RichiH/vcsh](https://github.com/RichiH/vcsh), I've decided to implement
[@RichiH](https://github.com/RichiH)'s `available.d/config.d` scheme.

That means that:

* `mr register` will add the configuration to
  `$XDG_CONFIG_HOME/mr/available.d/${REPO_NAME}.${REPO_TYPE}`

* `mr enable` and `mr disable` can be used to enable/disable repos from
  `available.d`.

## Original description

You have a lot of version control repositories. Sometimes you want to update
them all at once. Or push out all your local changes. You use special command
lines in some repositories to implement specific workflows.  Myrepos provides a
`mr` command, which is a tool to manage all your version control repositories.

It supports `git`, `svn`, `mercurial`, `bzr`, `darcs`, `cvs`, `fossil` and
`veracity`.

* Author: Joey Hess
* Homepage: http://myrepos.branchable.com/

The `mr` command is intended to be very self-contained, since it might be
useful to check it into `~/bin` when keeping your home in version control. It
has no dependencies aside from basic perl. (The included webcheckout command
has more dependencies, specifically the `LWP::Simple` and `HTML::Parser` CPAN
modules, and optionally the URI module.)

To install `mr`, just copy `mr` into your `PATH` somewhere.

To get started using `mr`, perhaps you already have some checked out
repositories. Go into each one and run `mr register`. Now `mr` has a list of
them in `~/.mrconfig`, which you can edit later to tune its operation.

Suppose you've cd'd to `~/src`, and it has many repositories under it.  To
update them all, run `mr update`. To commit any pending changes in each, run
`mr commit`. To check the status of each, you could run `mr status`.

For further details, and lots of configuration options, see the `mr(1)` man
page or the website, http://myrepos.branchable.com/
