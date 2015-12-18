Installing Drupal Using Composer Create-Project
===

Status
---
[![Build Status](https://travis-ci.org/paul-m/d8-create-project.svg?branch=master)](https://travis-ci.org/paul-m/d8-create-project)

What?
---

This test shows whether Drupal is modular enough to run PHPUnit tests from the command line and some SimpleTest tests, after using composer to install it using `create-project`.

It uses github and travis-ci to build a Drupal installation and then try to run tests.

We are limiting the tests to PHPUnit and one entity test, because otherwise travis will time out on us.

We are emulating this sequence of commands in travis-ci:

    $ composer create-project drupal/drupal drupal 8.0.*
    $ cd drupal
    $ ./vendor/bin/phpunit -c core/
    $ php ./core/scripts/run-tests.sh [more stuff] --class 'Drupal\system\Tests\Entity\EntityFieldTest'

How?
---

The travis-ci build happens whenever someone pushes to this repo. If you don't have access (and you don't), you can't push against this repo. Otherwise, you can choose from the following options:

* Fork your own repo, and push to your own repo to your heart's content. Please change the github OAuth token if you do.
* Perform the test locally. Just perform the commands listed in the What? section.
