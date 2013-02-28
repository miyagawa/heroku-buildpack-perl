Heroku buildpack: Perl
======================

This is a Heroku buildpack that runs any PSGI based web applications using Starman.

Usage
-----

Example usage:

    $ ls
    cpanfile
    app.psgi
    lib/

    $ cat cpanfile
    requires 'Plack', '1.0000';
    requires 'DBI', '1.6';

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

Dependencies can be declared using `cpanfile` or traditional `Makefile.PL` and `Build.PL`, and the buildpack will install these dependencies using [cpanm](http://cpanmin.us) into `./local` directory.
