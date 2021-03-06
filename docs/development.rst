Development
===========

Pull Requests
-------------

- Submit Pull Requests against the `master` branch.
- Provide a good description of what you're doing and why.
- Provide tests that cover your changes and try to run the tests locally first.

**Example**. Assuming you set up GitHub account, forked wheel repository from
https://github.com/pypa/wheel to your own page via web interface, and your
fork is located at https://github.com/yourname/wheel

::

  $ git clone git@github.com:pypa/wheel.git
  $ cd wheel
  # ...
  $ git diff
  $ git add <modified> ...
  $ git status
  $ git commit

You may reference relevant issues in commit messages (like #1259) to
make GitHub link issues and commits together, and with phrase like
"fixes #1259" you can even close relevant issues automatically. Now
push the changes to your fork::

  $ git push git@github.com:yourname/wheel.git

Open Pull Requests page at https://github.com/yourname/wheel/pulls and
click "New pull request". That's it.

Automated Testing
-----------------

All pull requests and merges to 'master' branch are tested in Travis_ based on
our `.travis.yml file`_.

Usually, a link to your specific travis build appears in pull requests, but if
not, you can find it on our `travis pull requests page`_.

The only way to trigger Travis to run again for a pull request is to submit
another change to the pull branch.

.. _Travis: https://travis-ci.org/
.. _.travis.yml file: https://github.com/pypa/wheel/blob/master/.travis.yml
.. _travis pull requests page: https://travis-ci.org/pypa/wheel/pull_requests

Running Tests
-------------

Python requirements: tox_ or pytest_

To run the tests locally::

  $ tox                     # Runs the tests against all matching interpreters
  $ tox -e py35             # Runs the tests against a specific environment
  $ pip install -e .[test]  # Installs the test dependencies locally
  $ pytest                  # Runs the tests with the current interpreter

.. _tox: https://pypi.org/project/tox/
.. _pytest: https://pypi.org/project/pytest/

Getting Involved
----------------

The wheel project welcomes help in the following ways:

- Making Pull Requests for code, tests, or docs.
- Commenting on open issues and pull requests.
- Helping to answer questions on the `mailing list`_.

.. _`mailing list`: https://mail.python.org/mailman/listinfo/distutils-sig

Release Process
---------------

#. Make sure there is a version block for this release in ``docs/news.rst``
   that mentions all the new user-facing changes
#. Add the version tag to the repository using ``git tag X.Y.Z``
   (e.g. ``git tag 1.0.1``)
#. Push the new tag to Github using ``git push --tags``

When a new tag is pushed to Github, Travis will pick it up and automatically
build the sdist and wheel and upload them to PyPI.
