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

See jujud commands available via `juju help-tool <command name>`.

#### action-get

```bash
Usage: action-get [options] [<key>[.<key>.<key>...]]
Purpose: get action parameters

options:
--format  (= smart)
    specify output format (json|smart|yaml)
-o, --output (= "")
    specify an output file

action-get will print the value of the parameter at the given key, serialized
as YAML.  If multiple keys are passed, action-get will recurse into the param
map as needed.
```

Ex. 1:
```bash
action-get --format=yaml
```
RESULTS:
```yaml
outfile:
  name: foo.gz
compression:
  kind: gzip
  quality: 3
```

#### action-set

```bash
usage: action-set <key>=<value> [<key>=<value> ...]
purpose: set action results

action-set adds the given values to the results map of the Action.  This map
is returned to the user after the completion of the Action.
```

Ex. 1:
```bash
action-set foo=5 bar=hello baz.x=3 baz.y=4
```

RESULT:
```yaml
foo: 5
bar: hello
baz:
  x: 3
  y: 4
```

Ex. 2:
```bash
action-set foo.bar=5 foo.bar.baz=outfile
action-set foo=5 
action-set bar.foo=3 bar.baz.foo=hello
action-set bar.baz.bar=4.3
```
RESULT:

```yaml
foo: 5 # Note foo got overwritten in the second invocation.
bar: 
  foo: 3
  baz: 
    foo: hello
    bar: 4.3
```

Ex. 3
```bash
action-set outfile.size=10G
action-set foo.bar=2
action-set foo.baz.val=3
action-set foo.bar.zab=4
action-set foo.baz=1
```
RESULT:
```yaml
outfile:
  size: "10G"
foo:
  bar:
    zab: "4"
  baz: "1"
```

#### action-fail

```bash
usage: action-fail ["<failure message>"]
purpose: set action fail status with message

action-fail sets the action's fail state with a given error message.  Using
action-fail without a failure message will set a default message indicating a
problem with the action.
```
