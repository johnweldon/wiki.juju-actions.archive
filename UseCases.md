





## API Oriented

###Discover list of Actions for a given Charm


1. User ‘asks’ for list of available Actions for a given Charm
1. ‘Juju’ (API) delegates request to a specific Unit of a Service of this Charm
1. Unit builds a list of the Actions by name and returns it
1. Client shows the list to the User

Variations:

1. No Actions are defined - Unit returns empty list






###Discover usage parameters for given Action


1. User asks for usage and parameters guidance for a given Action
1. API delegates request to specific Unit
1. Unit builds usage guidance from actions.yaml specification in the Charm, and returns it
1. Client displays usage

Variations:

1. Action has not been defined - Unit returns error response





###Queue an Action on a given Unit


1. User invokes Action and passes in Action specific parameters 
1. ...




###Queue an Action on a given Service


1. ...




###Discover list of previously queued Actions on a Unit


1. ...




###Discover list of previously queued Actions on a Service


1. ...




###Discover status of previously queued Action


1. ...




###Cancel a previously queued Action


1. ...




###Discover results of previously queued Actions


1. ...
