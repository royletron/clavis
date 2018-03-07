---
layout: term
title:  "Source Control Management (SCM)"
alternatives: [Version control, Revision control]
tags: [Application, Process, Development]
comments: true
---

_SCM_ refers to the management of the changes that developers make to a given `repository` of source code. Ensuring that changes are `merged` without overwriting concurrent changes, or that `conflicts` in changes are correctly managed by the developer. 

Source control systems commonly run as stand-alone applications and there are many different types of source control system the most notable ones being:

* git
* Subversion (or svn)
* Mercurial

The popularity of these systems has changed over time, but arguably `git` is the current 'de-facto' version control system of choice - though it is not uncommon for legacy projects to be hosted in other source control systems.

## Common usage

Most source control systems have the concept of `repositories` which effectively represents a collection of files that make up a logical project to whomever has created it. The `repository` is then `cloned` or `checked out` from the `remote` or `origin` - which is effectively the shared server for that `repository` to the developers local machine where they will work on the files. When a developer makes changes to the files these are tracked by the source control system locally on their machine until they are happy to share the changes with the rest of the team. Once at this point the developer must make a `commit` which pulls the changes together and wraps them up with a `message` that the developer will write - commonly they would explain the changes and why. This `commit` is then `pushed` back to the `origin` which will ensure that the `commit` is in line with it's own timeline of events - meaning if another developer has already made changes that `conflict` with the changes being `pushed` then the developer making the `push` must fix the `conflicts` before making a successful `push`. In pseudocode this would look as follows:

1. Developer A `clones` the `repository` from the `origin`
2. Developer A works on changes locally which are tracked by the source control system
3. Developer A decides the changes are good to share so makes a `commit` filling in a `commit message` explaining the changes
4. Developer A `pushes` the changes back to the `origin` which provided no `conflicts` exist is successful

_In the cases where there are `conflicts` Developer A will be prompted to make changes to their commit until the source control system can merge the changes together successfully_.