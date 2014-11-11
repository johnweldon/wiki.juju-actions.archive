## Motivation

Discuss the concrete schema for actions based on different examples.

## Schemas

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