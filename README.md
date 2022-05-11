 As solution for Release Strategy we can use [https://gitversion.net/](https://gitversion.net/)
 
 To use locally [download](https://github.com/GitTools/GitVersion/releases/tag/5.10.1) and add to path. And by typing gitversion in terminal while you are in repository directory you can see calculated version of your repository. 
 
 According to [https://gitversion.net/docs/learn/intro-to-semver](https://gitversion.net/docs/learn/intro-to-semver) Semantic Version can be achieved with two branching strategies:
1. [GitFlow](https://gitversion.net/docs/learn/branching-strategies/gitflow/examples) [main/master + develop + release branches]
2. [GitHubFlow](https://gitversion.net/docs/learn/branching-strategies/githubflow/examples) [main/master(mainline) + feature branches]

From my perspective GitFlow is most suitable for our project.

If we start from 1.0.0 on main and pull to develop, the current version will be 1.0.0-alpha.#, after the first commit to develop version will change to 1.1.0-alpha.#.

After pull requests and new features we want to release, we will create branch release/1.1.0 and push to remote. Pipeline will pick push to release/* and create pre-release with tag v1.1.0-beta.#.

When we are satisfied with the release we can merge to the main branch and pipeline will pick push to main build and create draft for main release v1.1.0 and only if we publish we will get tag v1.1.0.

EXAMPLE [https://github.com/mikara89/test](https://github.com/mikara89/test) 
