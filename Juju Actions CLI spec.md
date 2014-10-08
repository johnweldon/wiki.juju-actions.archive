## Contents
 - [Action commands](#action-commands)
   - `juju actions` list the available actions for a unit
   - `juju do`
   - `juju wait`
   - `juju queue`
   - `juju kill`
 - [Interacting with an Action](#interacting-with-an-action)
   - `juju status`
   - `juju log`
   - `juju fetch`
 - [Hook interaction](#hook-interaction)
   - `action-get`
   - `action-set`
   - `action-fail`

---

#### [Original Juju-Actions Draft spec](https://docs.google.com/document/d/14W1-QqB1pXZxyZW5QzFFoDwxxeQXBUzgj8IUkLId6cc/edit#heading=h.q6wtcjv2r9h)

---

# Action commands

#### juju actions \<unit name\>
A user can list the actions that a unit exports:
```
$ juju actions mysql
backup         benchmark      dump           ps             restart        
restore        start          stop           test
```
```
$ juju actions mysql/2
pause          resume         sync
```

#### juju do

#### juju wait

#### juju queue

#### juju kill

---

# Interacting with an Action

#### juju status

#### juju log

#### juju fetch

---

# Hook interaction

#### action-get

#### action-set

#### action-fail