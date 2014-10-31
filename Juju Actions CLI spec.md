## Contents
 - [Action commands](#action-commands)
   - `juju actions` list the available actions for a service
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

#### juju actions \<service name\>
A user can list the actions that a service exports:
```
$ juju actions mysql
backup         benchmark      dump           ps             restart        
restore        start          stop           test
```

#### juju do \<unit name\>
A user can trigger execution of a scripted action on a unit:
```
$ juju do mysql/2 pause 
finished
$ juju do mysql/3 backup --async
action: <UUID>
$ juju status <UUID>
result:
  status: success
  file: 
    size: 873.2 
    units: GB
    name: foo.sql
$ juju do mysql/3 backup --async --params parameters.yml
...
```

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