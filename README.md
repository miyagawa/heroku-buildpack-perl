Heroku buildpack: Perl
======================

This is a Heroku buildpack that runs any PSGI based web applications using Starman.

Usage
-----

Example usage:

    $ ls
    Makefile.PL
    app.psgi
    lib/

    $ heroku create --stack cedar --buildpack http://github.com/miyagawa/heroku-buildpack-perl.git

    $ git push heroku master
    ...
    -----> Heroku receiving push
    -----> Fetching custom buildpack
    -----> Perl/PSGI app detected
    -----> Installing dependencies

The buildpack will detect that your app has an `app.psgi` in the root.

Libraries
---------

Dependencies can be declared using either `Makefile.PL` or `Build.PL` (and `cpanfile` in the near future) and the buildpack will install these dependencies using [cpanm](http://cpanmin.us) into `./local` directory.
