
Steps for creating a new release
--------------------------------

  1. Cleanup code
  2. Review code
  3. Run tests
  4. Generate release notes
  5. Tag and create a new release
  6. Update project page


1. Cleanup code
---------------

[Convert to short array syntax](https://www.drupal.org/project/short_array_syntax)

    drush short-array-syntax short_array_syntax


2. Review code
--------------

[Online](http://pareview.sh)

    http://git.drupal.org/project/short_array_syntax.git 8.x-1.x

[Commandline](https://www.drupal.org/node/1587138)

    # Check Drupal coding standards
    phpcs --standard=Drupal --extensions=php,module,inc,install,test,profile,theme,js,css,info,txt,md,yml modules/sandbox/short_array_syntax

    # Check Drupal best practices
    phpcs --standard=DrupalPractice --extensions=php,module,inc,install,test,profile,theme,js,css,info,txt,md,yml modules/sandbox/short_array_syntax


3. Run tests
------------

[SimpleTest](https://www.drupal.org/node/645286)

    # Run all tests
    php core/scripts/run-tests.sh --url http://localhost/d8_dev --module short_array_syntax

[PHPUnit](https://www.drupal.org/node/2116263)

    # Execute individual PHPUnit tests.
    cd core
    php ../vendor/phpunit/phpunit/phpunit ../modules/sandbox/short_array_syntax/src/Tests/_ConfigUnitTest.php    


4. Generate release notes
-------------------------

[Git Release Notes for Drush](https://www.drupal.org/project/grn)

    drush release-notes 8.x-1.0-VERSION 8.x-1.x


5. Tag and create a new release
-------------------------------

[Tag a release](https://www.drupal.org/node/1066342)

    git tag 8.x-1.0-VERSION
    git push --tags
    git push origin tag 8.x-1.0-VERSION

[Create new release](https://www.drupal.org/node/add/project-release/2696073)


6. Update project page
----------------------

[Export README.md](https://www.drupal.org/project/readme)
    
     drush readme-export --project short_array_syntax

[Edit project page](https://www.drupal.org/node/2696073/edit)
