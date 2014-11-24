Juju Actions are a work in progress. This wiki will be a starting point to link all the development artifacts.
##[Juju Actions DRAFT spec](https://docs.google.com/document/d/14W1-QqB1pXZxyZW5QzFFoDwxxeQXBUzgj8IUkLId6cc/view)
##[See doc/actions.md for more details](https://github.com/juju-actions/juju/blob/actions/doc/actions.md).

# Status

> Demo CLI for review
 - [#8 `juju actions`](https://github.com/juju-actions/juju/pull/8)

---

> Pending Reviews:
 - `@binary132` [PR #945](https://github.com/juju/juju/pull/945) -- Add `juju actions` command to CLI

---

> In progress:
 - `@johnweldon` Refactoring API

## State

 - [x] actionDoc, actionResultDoc
 - [x] watcher
 - [x] cleanup

## Action commands

 - [x] action-get
 - [x] action-set
 - [x] action-fail

## Uniter

 - [x] Listen for Actions for unit
 - [x] Fire actions
 - [x] Return results
 - [x] Handle Action error states

## API
API includes the apiserver, and api (client) packages.

 - [x] List Actions
 - [x] Enqueue Actions
 - [x] Cancel Actions
 - [x] Describe available Actions
 - [x] Find Actions matching short UUID prefix
 - [ ] Archive Actions?

## CLI

 - [x] actions **[PR #945](https://github.com/juju/juju/pull/945)**
 - [ ] status
 - [ ] log
 - [ ] fetch
 - [ ] do
 - [ ] archive?
 - [ ] kill
 - [ ] queue
 - [ ] wait

## Refactoring

[Refactoring Issues](https://github.com/juju-actions/juju/issues?q=is%3Aopen+is%3Aissue+label%3Arefactoring)

 - [x] [include timestamps](https://github.com/juju-actions/juju/issues/6) **in progress**
 - [ ] [require name in action](https://github.com/juju-actions/juju/issues/7) 

# Links

[[Juju Actions CLI spec]]

[[API]] Docs

[[Use Cases]]