# Contribution Guide

If you have any comment or advice, please report your [issue](https://github.com/abhir9/Egnature/issues),
or make any change as you wish and submit a [PR](https://github.com/abhir9/Egnature/pulls).

## Reporting New Issues

- Please specify what kind of issue it is.
- Before you report an issue, please search for related issues. Make sure you are not going to open a duplicate issue.
- Explain your purpose clearly in tags(see **Useful Tags**), title, or content.

 Group members will confirm the purpose of the issue, replace more accurate tags for it, identify related milestone, and assign developers working on it.

- Type: What kind of issue, e.g. `feature`, `bug`, `documentation`, `performance`, `support` ...

### Useful Tags

- `support`: the issue asks helps from developers of our group. If you need helps to locate and handle problems or have any idea to improve Egnature, mark it as `support`.
- `bug`: if you find a problem which possiblly could be a bug, please tag it as `bug`. Then our group members will review that issue. If it is confirmed as a bug by our group member, this issue will be tagged as `confirmed`.
  - A confirmed bug will be resolved prior.
  - If the bug has negative impact on running online application, it will be tagged as `critical`, which refers to top priority, and will be fixed ASAP!
  - A bug will be fixed from lowest necessary version, e.g. A bug needs to be fixed from 0.9.x, then this issue will be tagged as `0.9`, `0.10`, `1.0`, `1.1`, referring that the bug is required to be fixed in those versions.

## Documentation

All features must be submitted along with documentations. The documentations should satify several requirements.

- Documentations must clarify one or more aspects of the feature, depending on the nature of feature: what it is, why it happens and how it works.
- It's better to include a series of procedues to explain how to fix the problem. You are also encourgaed to provide **simple, but self-explanatory** demo.
- Please provide essential urls, such as application process, terminology explainations and references.

## Submitting Code

### Pull Request Guide

If you are developer of egnature repo and you are willing to contribute, feel free to create a new branch, finish your modification and submit a PR.  Group will review your work and merge it to master branch.

```bash
# Create a new branch for development. The name of branch should be semantic, avoiding words like 'update' or 'tmp'. We suggest to use feature/xxx, if the modification is about to implement a new feature.
$ git checkout -b branch-name

# If your modification pass the tests, congradulations it's time to push your work back to us. Notice that the commit message should be wirtten in the following format.
$ git add . # git add -u to delete files
$ git commit -m "fix(role): role.use must xxx"
$ git push origin branch-name
```

Then you can create a Pull Request at [Egnature](https://github.com/abhir9/Egnature/pulls)

No one can garantee how much will be remembered about certain PR after some time. To make sure we can easily recap what happened previously, please provide the following information in your PR.

1. Need: What function you want to achieve (Generally, please point out which issue is related).
2. Updating Reason: Different with issue. Briefly describe your reason and logic about why you need to make such modification.
3. Related Testing: Briefly descirbe what part of testing is relevant to your modification.
4. User Tips: Notice for Egnature users. You can skip this part, if the PR is not about update in API or potential compatibility problem.

### Commit Message Format

You are encouraged to use [angular commit-message-format](https://github.com/angular/angular.js/blob/master/DEVELOPERS.md#-git-commit-guidelines) to write commit message. In this way, we could have a more trackable history and an automatically generated changelog.

```xml
<type>(<scope>): <subject>
<BLANK LINE>
<body>
<BLANK LINE>
<footer>
```

（1）type

Must be one of the following:

- feat: A new feature
- fix: A bug fix
- docs: Documentation-only changes
- style: Changes that do not affect the meaning of the code (white-space, formatting, missing semi-colons, etc)
- refactor: A code change that neither fixes a bug nor adds a feature
- perf: A code change that improves performance
- test: Adding missing tests
- chore: Changes to the build process or auxiliary tools and libraries such as documentation generation
- deps: Updates about dependencies

（2）scope

The scope could be anything specifying place of the commit change. For example avatar-editor, dropzone etc...

（3）subject

Use succinct words to describe what did you do in the commit change.

（4）body

Feel free to add more content in the body, if you think subject is not self-explanatory enough, such as what it is the purpose or reasone of you commit.

（5）footer

- **If the commit is a Breaking Change, please note it clearly in this part.**
- related issues, like `Closes #1, Closes #2, #3`
- If there is a change about an old feaure or a new feature, please associate `doc` and `engature-core`, like `abhir9/Egnature-core#123`

e.g.

```
fix($compile): [BREAKING_CHANGE] couple of unit tests for IE9

Older IEs serialize html uppercased, but IE9 does not...
Would be better to expect case insensitive, unfortunately jasmine does
not allow to user regexps for throw expectations.

Document change on abhir9/Egnature#123

Closes #392

BREAKING CHANGE:

  Breaks foo.bar api, foo.baz should be used instead
```

