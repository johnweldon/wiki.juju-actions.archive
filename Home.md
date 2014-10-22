Juju Actions are a work in progress. This wiki will be a starting point to link all the development artifacts.

# Status

> Demo CLI for review
 - [#8 `juju actions`](https://github.com/juju-actions/juju/pull/8)

---

> Pending Reviews:
 - `@binary132` [PR #945](https://github.com/juju/juju/pull/945) -- Add `juju actions` command to CLI

---

> In progress:
 - `@johnweldon` Refactoring timestamps

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
 - [ ] Archive Actions?

## CLI

 - [ ] actions **in progress**
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

 - [ ] [include timestamps](https://github.com/juju-actions/juju/issues/6) **in progress**
 - [ ] [require name in action](https://github.com/juju-actions/juju/issues/7) 

# Links

[[Juju Actions CLI spec]]

[[API]] Docs

[[Use Cases]]