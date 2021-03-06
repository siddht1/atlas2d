
# Atlas 2D Client-Server API
This document provides the second most up to date description of the data structures used on the client and server (the first being the source code).

## Definitions
These are structures that are referred to by name in this document.

### component
A component can be any JSON value you like: an object, array, or scalar.
For some commands, you can send partial "diffs" of components,
and the client will merge the new values with the old ones.

### entity
An entity is only made up of named components.
Every entity has a unique ID (a Number or String), but it is not sent
in the entity object itself.

{
  <component-name>: <component>,
  ...
}



## Commands (server --> client)
Commands are sent from the server to the client as JSON objects.
Each command is a JSON object, with the 'cmd' key as the name of the
command and the arguments specified with their keys.


### Entity CUD (Create, Update, Delete)

{
  cmd: "entityCreate",
  id: ID,
  entity: <entity>
}

{
  cmd: "entityUpdate",
  id: ID,
  entity: <partial-entity>
}

{
  cmd: "entityDelete",
  id: ID
}

### Player

{
  cmd: "playerSet",
  id: ID
}



## Requests (client --> server)


### 