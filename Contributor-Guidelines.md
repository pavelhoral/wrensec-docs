## Introduction
Thank you for your interest in contributing to Wren Security. We appreciate all help with finding and fixing bugs, making performance improvements, and other tasks. Every contribution is helpful and we thank you for your effort. To ensure the process of contributing is as smooth as possible, here are a few guidelines for you to follow.

## Getting Started
### Fork Our Repository
All contributions to Wren Security should be made via GitHub pull requests, which require that the contributions be offered from a fork of the appropriate Wren Security project repository.

For help with forking a repository, refer to GitHub [Fork a Repo](https://help.github.com/articles/fork-a-repo/ "Fork a Repo").

### Ensure Your Copy is Buildable
Before you start to make changes, make sure that you have a functional build of the project to start from. This can help prevent future misunderstandings that result from starting off of unstable code.

To make sure that the build you have is functional, run the tests included in the project prior to starting work on your new feature. Instructions on how to run the tests should be part of the project's README file.

## Development
### Workflow
1. **Check out the Latest Changes from the `master` Branch**  
```bash
$ git checkout master
# Assuming that `wren` is your remote name for Wren's copy of the project 
$ git pull wren master
```
2. **Create a Feature Branch**  
```
$ git checkout -b feature/my-awesome-improvement
```
3. **Make and Commit Changes**  
Edit the source and commit the changes you make in logical chunks (see [Commit Guidelines](#commit-guidelines) below). All changes &ndash; including new features and bug fixes &ndash; must include tests that demonstrate that the changes work as expected, unless there is no practical way to test the issue being corrected.
4. **Push to Your Fork**  
In order to submit a pull request, you must push your local branch to your fork of the repository on GitHub.
```
$ git push origin feature/my-awesome-improvement
```
5. **Submit a Pull Request**  
Submit a pull request from your feature branch onto the target branch of the Wren Security project (See GitHub [Using Pull Requests](https://help.github.com/articles/about-pull-requests/ "Using Pull Requests")).
6. **Respond to Pull Request Feedback on the Same Branch**  
If and when maintainers ask for you to make changes to your work, you should be sure to make the requested changes on the _same feature branch_ that contains your original changes. Then, unless the maintainers have specifically asked you to do otherwise, push to _the same branch_ on your remote from which your pull request originates, and do _not_ create a new pull request for the new changes. Your existing pull request should automatically reflected the new changes you pushed.

### Commit Guidelines
We encourage many smaller commits over one large commit. Small, focused commits make the review process easier and are more likely to be accepted. It is also important to summarize the changes made with brief commit messages. If a commit fixes a specific issue, it is also good to note that in the commit message.

The commit message should start with a single line that briefly describes the changes. That should be followed by a blank line and then a more detailed explanation. As a good practice, use commands when writing the message (instead of "I added ..." or "Adding ...", use "Add ...").

Before committing. check for unnecessary whitespace with `git diff --check`.

Additionally, we ask that you please review the following guides before making your first commit, to encourage maintainability:

* [How to Write a Git Commit Message](https://chris.beams.io/posts/git-commit/)
* [Git Commit Best Practices](https://wiki.openstack.org/wiki/GitCommitMessages)
* [A Note About Git Commit Messages](https://tbaggery.com/2008/04/19/a-note-about-git-commit-messages.html)
* [Git Commit Guidelines](https://git-scm.com/book/en/v2/Distributed-Git-Contributing-to-a-Project)

## Submitting Changes
### Pull Request Guidelines
The following guidelines can increase the likelihood that your pull request will get accepted:
* Work on a separate branch for each distinct feature or bug-fix.
* Follow all applicable [style guides](https://github.com/WrenSecurity/wrensec-docs/wiki/Coding-Standards-&-Style-Guides) when writing your code.
* Follow the [Commit Guidelines](#commit-guidelines) when committing your code.
* Keep patches on topic, focused, and atomic.
* Try to avoid unnecessary formatting and clean-up, where reasonable. (For Java code, see [section 8.3 of the Wren Java Style Guide](https://github.com/WrenSecurity/wrensec-docs/wiki/Java-Style-Guide#83-code-not-in-wren-style); for JavaScript code, see [section 8.3 of the Wren JavaScript Style Guide](https://github.com/WrenSecurity/wrensec-docs/wiki/JavaScript-Style-Guide#83-code-not-in-wren-style)).
* Write tests that cover all the code your change affects.

A pull request should contain the following:
* At least one commit (all of which should follow the [Commit Guidelines](#commit-guidelines)).
* Title that summarizes the issue.
* Description that briefly summarizes the changes.

After submitting a pull request, you should get a response within the next 7 days. If you do not, please do not hesitate to ping us in the Pull Request thread, [on Gitter](https://gitter.im/WrenSecurity/Lobby), or in [the Wren Security Google Group](https://groups.google.com/forum/#!forum/wren-security).

***
# Credits
This set of guidelines was inspired by the [Contributor Guidelines](https://apereo.github.io/cas/developer/Contributor-Guidelines.html) for CAS by Apereo.