## Motivation

Discuss the concrete schema for actions based on different examples.

## TOC

 - [Current Spec](#current-spec)
 - [Database Foo](#database-foo)

## Schemas

### Current Spec

```yaml
# actions.yaml
actions:
  snapshot:
    description: Take a snapshot of the database.
    params:
      title: Snapshot params
      description: Arguments to snapshot.
      type: object
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