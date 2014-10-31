# Summary

## API Methods - Client facing

- Enqueue
- ListAll
- ListCompleted
- ListPending
- Cancel
- ServiceCharmActions
- WatchActions

## API Methods - internal/Jujud facing

- GetActions
- StartActions (maybe UpdateActions, or ActionsUpdate?)
- FinishActions
- WatchActions

# Details

## Client Facing

### Enqueue

`Enqueue` takes a list of `Actions` and queues them up to be executed by the designated receiver, returning `ActionResults` for each queued Action, or an error if there was a problem queueing up the Action. 

### ListAll

`ListAll` takes a list of `Tags` representing receivers and returns all of the `Actions` that have been 
queued or run by each of those entities as `ActionsByReceivers`.

### ListCompleted

`ListCompleted` takes a list of `Tags` representing receivers and returns all of the `Actions` that have been run on each of those entities as `ActionsByReceivers`.

### ListPending

`ListPending` takes a list of `Tags` representing receivers and returns all of the `Actions` that are queued for each of those entities as `ActionsByReceivers`.

### Cancel

`Cancel` attempts to cancel queued up Actions from running. `ActionTags` are passed as argument, `ActionResults` are returned.

### ServiceCharmActions

`ServicesCharmActions` returns the `ServicesCharmActionsResults` for the passed `ServiceTags`. 

### WatchActions

:question:

## Internal/Jujud Facing

### GetActions

:question:

### StartActions

:question:

### FinishActions

:question:

### WatchActions

:question:
