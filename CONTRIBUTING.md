# Contributing Guide

This document aims to describe the workflows and rules used for developing the projects under the
TypeStack organization. This includes but not limited to:

- guidelines how open issues about requested features or bug reports
- how issues should be handled by maintainers (labeling, when to close issues, etc.)
- general guidelines for how to contribute code

> __Note:__ This general guide is referenced in every project-specific guide. Please read both guides
> before contributing to any project to prevent duplicated work and misunderstandings.

## Terminology

We group people interacting with the TypeStack repositories into 4 categories:

- __user__ - developers who use any of our projects and may or may not participate in discussions regarding a given project
- __contributor__ - someone who helped to improve any of the projects but has no push access to the project
- __maintainer__ - people added to the TypeStack organization who actively contribute to our projects and has direct push access
- __owner__ - the owners of the TypeStack organization with full admin rights

A valuable __contribution__ can be many other things than adding code, it also includes:

- opening bug reports with reproducible steps
- engaging in discussions for new feature requests
- helping with answering questions
- contributing fixes for code or documentation
- contributing code for new features

## Scope of project

Each project has it's scope defined in its respective contributing guideline. Code contributions are only accepted
for changes fitting the scope of the project. If you find yourself in a need of some functionality that is currently
not in scope for the project please open an issue first to discuss your needs and your rationale/reasoning to add the feature.

## Responsibilities and rights of groups

Anyone who interacts must confront the basic responsibility of not being a jerk. Stay polite and focus the discussions
on the project and the technical aspects.

### Responsibilities of a maintainer

As a maintainer you have some extra responsibilities:

- help users to reach their goal while using the library via answering their questions
- prioritize your time on the more important things first
- ensure only changes inside of the project scope gets added in the project
- see every change request with a critical mindset: how this can break current workflows, what does this aims to solve,
does the problem real or caused by user error?

### The rights of the maintainers

- push code to the project repository
- merge PRs into the protected branches (`develop`, `master`)
- label, close, re-open issues
- release a new version of the project

## Handling issues

Helping the _users_ of the project is the most important task of a _maintainer_. Answering questions should take priority
over coding. Every issue should be handled first as a question (even if it was opened as a bug report or feature request).
A significant part of the feature requests and bug reports are usage related questions where the _user_ either
haven't read the documentation of the desired functionality or attempting to use invalid configuration.

### Opening issues

Before opening an issue please make sure, you have:

- read the documentation
- searched open issues for an existing issue with the same topic
- search closed issues for a solution or feedback

If you haven't found any _related open issue_, please open a new one. A well-written issue has the following traits:

- follows the issue template
- contains the reasoning or description of the feature or fix
- contains a minimal, inlined code example showcasing the problem of the proposed feature
- includes links to prior discussion if you have found any
- uses proper English, if you are not a native speaker (neither most of us) and you have grammar mistakes that are not a problem,
but take your time and write the description as good as you can, low effort posts may be closed without further comment

### Labelling issues

We use a well-defined list of labels to organize the issues opened in the TypeStack repositories. Labels are grouped into
different categories (identified by the prefix, eg: `status:`).

### List of labels

Below you can find the detailed list of labels we use for issue management and their purpose.

#### Type labels

Every opened issue has a type, assigned after creation. It is uncommon to change the type label on an issue but
can happen for example when a feature request is re-classified as a question. We have the following types:

`type: question`  
This is the most common issue type. Any question regarding the usage of the library is a question.
__Also a decent bit of bug reports are usage questions, as the user who asking hasn't read/follow the documentation,
so don't be afraid to change a feature request or bug report into a question if you believe the described
scenario can be achieved with the current version of the library.

`type: feature`  
Issues requesting new features with a clear initial definition of what that feature should be. The proposal may be
changed during the discussion before the implementation.

`type: fix`  
Bug reports about existing (documented) functionality in the library.

`type: discussion`  
Issues where the community can start iterating over ideas that are not yet exactly defined. The output of a discussion
ticket should be one or more new feature request tickets after an agreement is reached on what the given functionality
should be.

`type: documentation`  
Special issues, mostly opened by the _maintainer(s)_ to track documentation changes, but also can be assigned to issues
where a user asks for more detailed documentation about a public API.

`type: build`  
Issues about the project tooling not related to the source code.

#### Status labels

During an issue's life-cycle it must always have a single `status: *` label which reflects the current state of the issue.
Currently, we differentiate between the following statuses:

`status: needs triage`  
Typically bug reports will be marked as needs-triage until a _maintainer_ verifies the issue
and posts a minimal reproduction use-case as an __inline code snippet__ to be used as a reference.

`status: cannot reproduce`  
This label is assigned when the bug report cannot be reproduced by the _maintainer(s)_. An issue marked
with this label can be closed.

`status: awaiting answers`  
This label is assigned to every question, feature request, bug, or any other issue where
the _maintainer(s)_ engaged in the discussion needs clarification from the original poster.

`status: has PR`  
The issue has ongoing work in an open PR. This is basically a "reserve" label to prevent duplicate work.

`status: fixed`  
The issue has been fixed and merged into `develop`, but not has been released yet. Issues __should not be closed__ until
the fix or feature is released.

`status: done / released`
The issue has been released, the issue can be closed.

`status: blocked`  
The task in the given issue is blocked by some other work tracked in a different issue. When this label added the
blocking issue should be referenced in a comment on the issue.  

`status: duplicate`  
The task is already tracked in a different issue. When adding this label a reference should be added as a comment to
the issue tracking the task.

`status: invalid`  
When there is no action to take by a maintainer the issue will be marked as invalid and closed. Common examples for
these are issues written any language other than English, code snippets posted without explanation, and title only issues.

`status: wontfix`  
Proposals not fitting into the scope of the project will be closed with this label, signaling that the requested feature
won't be implemented.

#### Component labels

Components labels are project-specific and defined for every project. They represent major parts of the given project.
Some examples would be: `comp: core` or `comp: decorators`.

#### Flag labels

These labels can be assigned to issues or PRs to indicate additional work.

`flag: refactor needed`  
This flag can be assigned to PRs signaling that the implementation is not acceptable and should be reworked before being merged.

`flag: needs docs`  
The given issue or PR lacks the required documentation changes. These should be added. After the required documentation
is added the label should be removed from the issue or PR.

`flag: needs discussion`  
The issue or PR __requires further discussion before implementation__ as it doesn't meet technical or some other
requirement.

`flag: accepting PR`
We are accepting PR to resolve given issue.

`flag: BREAKING CHANGE`  
The issue or PR contains a breaking change that requires a major version bump.

### Locking conversation on closed issues

We use a CI action to close issues which are closed and has no activity in the last 30 day. If you found a closed issue
about your problem please open a new issue and reference the closed issue in your description.

## Contributing code

In general, any code to be accepted into the default branch must confront the following criteria:

- the proposed changes should be discussed prior to implementation
- the proposed changes should have a related tracking issue which is referenced in the PR
- the required checks on the PR must pass (preferably the optional checks also)
- must have at least two accepted code review from _maintainers_ or a single accepted review from _project owner_
- the provided code must be tested properly
- the change should include documentation changes if applicable  

### Discussion before implementation

One of the most important rules of code contribution is to __discuss your changes in advance__! You must open a separate
issue (not PR) and propose the desired changes before implementation for any non-trivial change. This is required so we
can prevent duplicated work and rejected PRs.

In short, most PRs will be blocked immediately if it has no tracking issue or belongs to an issue that has the
`flag: needs discussion` label. (Some very minor changes like a typo fix may be opened without opening a tracking issue.)

### Opening PRs and code reviews

When you have created an implementation for a feature that has been discussed and approved by a _maintainer_, you need
to open a PR against the default (`develop`) branch on the repository. Every opened PR should

- follow the PR template
- reference it's tracking issue

_Note_: We suggest to enable the setting in the PR which allows the _maintainers_ to push to the given branch. This
will allow them to push quick fixes to the branch before merging instead of asking you to do it.  

After you have created the PR it will be reviewed by one or more _maintainers_. They may request some extra changes to
be made. When all reviewers approved the PR will get merged and included in the next release.

### Commit guidelines

We use the lite version [Angular commit message guidelines][angular-commit-guidelines] for our commit messages.
This means every commit must confront the header format:

```text
<type>(<scope>): <short summary>
  │       │             │
  │       │             └─⫸ Summary in present tense. Not capitalized. No period at the end.
  │       │
  │       └─⫸ Commit Scope: defined by the project contributing guidelines
  │
  └─⫸ Commit Type: build|ci|docs|feat|fix|perf|refactor|style|test
```

The `<type>` and `<summary>` fields are mandatory, the (`<scope>`) field is optional.

> __Note:__ The project-specific scopes can be found in the project-specific contribution guides.  

The `<type>` must be one of the following values:

- `feat`: A new feature
- `fix`: A bug fix
- `refactor`: A code change that neither fixes a bug nor adds a feature
- `test`: Adding missing tests or correcting existing tests
- `docs`: Documentation only changes
- `perf`: A code change that improves performance
- `build`: Changes that affect the build system or external dependencies
- `ci`: Changes to our CI configuration files and scripts

### Disallowed code contributions

Some areas are managed centrally through the organization and don't accept code contributions from _contributors_ or
_maintainers_. This doesn't mean you cannot open issues to propose or discuss changes to these areas, but the code
itself will be added by a _project owner_ most of the time. Proposed changes to these areas must have strong reasoning
on why they should be changed.

These areas currently include:

- our CI configuration
- some of our used dev dependencies:
  - testing framework (Jest)
  - code coverage tool (Codecov)
  - code formatting and it's configuration (Prettier)
  - our linter (ESLint)

### Merging PRs

In every repository to merge option is enabled: squash and merge.

- if a PR has a single commit or the changes across commits are logically grouped use squash
- if a PR has multiple commits which are not logically grouped together use a merge commit

When merging please make sure to use the following merge commit message format:

```text
merge: <summary of changes> (#<GH issue number>)
```

## Releasing

Every repository under the TypeStack organization is configured to release a new version from the project when a
Github Release is created from a tag. This means any member with push access can create a release.

> __Note:__ The actual NPM publish is made by a bot from the source code on Github so invalid or malicious versions cannot be
released by any _maintainer_ without merging those changes into the `master` branch first. (What would be discovered.)

Before a release the following steps must be done:

- decide what version bump this release needs (patch, minor, major)
- changelog is added in a comment for the given release (issues w/ `status: merged`)
  - the commit should be named `docs: add changelog for <x>.<x>.<x>`
  - the commit should contain only the changelog change
- the version number is raised in `package.json`
  - the commit should be named `build: bump version to <x>.<x>.<x>`
  - the commit should contain only the version bump change
- a new PR is opened from `develop` into `master`
  - the PR should be titled `release: <x>.<x>.<x>`
  - after review, the PR __should be merged with a merge commit__ named `merge: release <x>.<x>.<x>`
- the git tag with the same version is added to the merge commit (this can be done locally or on Github)
  - the git tag must have the `v` prefix and the version number, eg: `v1.4.2`
- a release is created from the git tag on Github
- the maintainer who merged the release PR should wait and see if the CD task successfully releases the project to NPM
- all issues w/ `status: merged` label released in this version should be closed as done

[angular-commit-guidelines]: https://github.com/angular/angular/blob/master/CONTRIBUTING.md#-commit-message-format
