
# Tutorial: Adding automated tests to a Python project

Code that's not tested is probably broken. Here's how to quickly add an
automated unit test to any Python project to get you started:

## Part one: Add a test to one of your Python projects

1. Pick any of your Python projects. Pick a messy one.
2. Wow, that one is dirty. Good. Create a folder named `tests` in the project
   directory.
3. Add a file named `__init__.py` in the `tests/` directory. Leave it empty.
4. Pick any Python function in your project. Pick a simple one that's easy to
   call without too much context. For this particular project I'll pick
   `hellopy.greetme.greetme`.
5. Add a file that named `test_YOURFUNCTION.py` in the `tests/` directory. I
   named it `test_greetme.py` for obvious reasons. Open the file in an editor.
6. Look at [`tests/test_greetme.py`](tests/test_greetme.py) in this repository,
   copy it over and make it call the function you have picked. The
   [unittest](https://docs.python.org/3/library/unittest.html) documentation
   will tell you all the ways you can test your function. It's enough to have
   the test just call your function for now. If that succeeds your code is at
   least not entirely broken.
7. Run `python3 -m unittest -v` in your project directory. It will automatically
   find your new test and run it. Your project has unit tests now. Good start!

## Part two: Put the project on GitHub and have it automatically run your tests

1. [Create a new repository on GitHub](https://github.com/new) for your project,
   if you haven't already. You can make it private if you don't want the world
   to see your messy code.
2. Push your code to the GitHub repository. Follow GitHub's instructions to do
   that (or not).
3. Add a folder named `.github` in your project directory (note the leading
   `.`), add another folder named `workflows` inside `.github/`, and inside that
   one add a file named `Tests.yaml`. That's `.github/workflows/Tests.yaml`.
4. Look at [`.github/workflows/Tests.yaml`](.github/workflows/Tests.yaml) in
   this repository and copy it over. No need to change anything for now.
5. Commit and push. Now go to your repository page on GitHub and click
   "Actions". Your tests are running automatically!
6. From now on the tests will run over every commit you push to GitHub, making
   sure you don't accidentally break anything. Done!

## Part three: Go from here!

1. Look at the [unittest](https://docs.python.org/3/library/unittest.html)
   documentation for information on writing more tests. You may also find the
   [numpy.testing](https://numpy.org/doc/stable/reference/routines.testing.html)
   module useful to test your NumPy code.
2. Look at GitHub's guide on [Building and testing
   Python](https://docs.github.com/en/actions/guides/building-and-testing-python)
   for information on automating your tests.
3. If you're working together with others on the project, consider [opening
   pull-requests](https://docs.github.com/en/github/collaborating-with-issues-and-pull-requests/about-pull-requests)
   for changes instead of pushing commits directly. That gives others a chance
   to look over the proposed changes before merging them. It also automatically
   runs your tests and reports if the proposed changes break anything.
4. Add more tests to your project whenever you feel like it. It's a good idea
   to add a test every time you add a new function.
5. Remember: If you find a function is hard to test because it's so complicated
   to set up, then you should probably split it into smaller, more independent
   functions and test those. It's good for you and good for your tests!
