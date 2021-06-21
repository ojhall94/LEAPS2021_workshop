# Topic 3: Collaborative GitHub

*Warning*: Make sure you go through Topic 1 briefly before jumping into this one. It will require understanding the tools explained there!

As mentioned in Topic 1, GitHub can be an incredible collaborative tool. Almost all open source programs are built here. This is particularly because GitHub allows for individuals to easily contribute to a project, by opening Pull Requests with features they would like to see added, and by raising issues for developers to address.

This portion of the workshop is really cheating a little bit--- I will be outsourcing this to [Dr. Christina Hedges](https://github.com/christinahedges)'s excellent workshop on collaborative astronomy efforts. Dr. Hedges is one of the core developers on the massive open source tool [Lightkurve](https://github.com/lightkurve/lightkurve), as well as a ton of other open source code, and explains this stuff better than I ever could!

Her full workshop can be found below. It covers all the basics of GitHub all the way through to the section on Testing. You'll want to read past that when it comes to publishing an open source code, but for now let's settle for collaborative working.
https://christinahedges.github.io/astronomy_workflow/index.html

Ideally, I want those of you working on this topic to collaborate on a tiny Python function. See if, using the tutorials linked above, you can work down the following checklist:

## Checklist
- [ ] Assign a project lead, who forks this repository
- [ ] All team members clone this forked repository
- [ ] Create a Python script with a function for one simple task
  - This could be returning the square of your input, or returning 'Hello World'
- [ ] Write a test for this function
  - Get it to return `True` if the function works, and `False` if it doesn't.
- [ ] Open a Pull Request to `ojhall94/LEAPS2021_workshop`
- [ ] Work together on the Pull Request to perform a review of the changes.


### Forking
When you `fork` a repository, you are essentially creating a copy of it that is hosted on *your* GitHub account. This repository is still linked to the original, but now you have the admin rights over your fork. This lets you work on major projects, such as `Lightkurve`, without needing access rights to the core repository.

The person who has cloned the repository can provide their collaborators with the link, so they can clone it. You can also add your collaborators to the repository using Settings -> Manage Access on GitHub.


### Writing Tests
When working on major codes, it is super important to write so-called "unit tests". These simple tests can be run whenever you want, and check that the code works, even after the changes you've just made to it. Ideally, you want to make sure that your tests are so complete that every line of code you've written is called, so nothing can slip through the cracks.

Usually, unit tests are set up in such a way that you can call them using the `pytest` program from commandline. Often (especially for major collaborations), when you open a Pull Request GitHub itself will run tests, and not allow the Pull Request to be merged until the tests come back without errors! This stops functional code that people depend on from being broken.

For this little workshop, don't worry about calling your functions from Pytest (unless you want to of course--- there's an explanation in Dr. Hedges's tutorial). Just focus on making sure you have a test that returns True/False, and calls every line of the code in your function!

### Opening and reviewing a pull request
When I work on a new feature for an open source project, I make a fork and then immediately open a Pull Request to main! This doesn't mean I have to immediately merge my code--- the Pull Request can serve as a history of the work I've done. It also lets other people check and different parts of the process to give their input. [Lightkurve has some great examples of this](https://github.com/lightkurve/lightkurve/pull/625). In this thread, the author made a new feature, recieved input from multiple collaborators, and then made subsequent changes to the code that improved it!

You can add your own review to any pull request by going to the 'Files Changed' tab, and leaving comments on the code! Don't be afraid to give your input by commenting on the PR, either.


### And one more thing...
I haven't covered reporting Issues in this tutorial. I won't go into depth on it here, but if you'd like to see how the issue resolution process works (and how Issues and Pull Requests are interactively linked on GitHub!), [have a look at the closed issues on Lightkurve](https://github.com/lightkurve/lightkurve/issues?q=is%3Aissue+is%3Aclosed)!
