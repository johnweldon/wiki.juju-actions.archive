## Motivation

Discuss the concrete schema for actions based on different examples.

## TOC

 - [How William wants it](#williams-version)
 - [Current Spec](#current-spec)
 - [Database Foo](#database-foo)

## Schemas

### William's version

In this version, some values from within the schema are mapped to values in the containing type.

Differences:
 - Description field will be mapped to "description" field of params
 - Params Will be mapped to root map for action; type "object" assumed
 - Title will be added from the name for the action

```yaml
# actions.yaml
snapshot:                                        # Name of the action script.
  description: Take a snapshot of the database.  # charm.Actions.ActionSpecs["snapshot"].Description
  params:                                        # charm.Actions.ActionSpecs["snapshot"].Params
    outfile:
      description: The file to write out to.
      type: string
      compression:
        description: How to compress the outfile.
        type: object
        properties:
          kind:
            description: The utility to compress with.
            type: string
            enum: [gzip, bzip2, xz]
          quality:
            description: Compression quality
            type: integer
            minimum: 0
            maximum: 9
    required: [outfile]
kill:
  description: Kill the database.
```

### Current Spec

```yaml
# actions.yaml
actions:                                           # Go representation:
  snapshot:                                        # Name of the action script.
    description: Take a snapshot of the database.  # charm.Actions.ActionSpecs["snapshot"].Description
    params:                                        # charm.Actions.ActionSpecs["snapshot"].Params
      title: Snapshot params                       # map[string]interface{} representing JSON-Schema.
      description: Arguments to snapshot.          # Note that this is valid JSON-Schema with
      type: object                                 # $schema keys stripped.
      properties:
        outfile:
          description: The file to write out to.
          type: string
        compression:
          description: How to compress the outfile.
          type: object
          properties:
            kind:
              description: The utility to compress with.
              type: string
              enum: [gzip, bzip2, xz]
            quality:
              description: Compression quality
              type: integer
              minimum: 0
              maximum: 9
      required: [outfile]
  kill:
    description: Kill the database.
```

### Database Foo

```yaml
# actions.yaml
actions:
  snapshot:
    description: Take a snapshot of the database.
    properties:
      outfile:
        description: The file to write out to.
        type: string
      compression:
        description: Optional compression of the outfile.
        properties:
          quality:
            description: Compression quality
            type: integer
            minimum: 0
            maximum: 9
          format:
            description: Outfile format
            type: oneof
            values:
            - gz
            - zip
      required: [outfile]
  kill:
    description: Kill the database.
```