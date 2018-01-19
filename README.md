# Bldr resource

a Concourse resource for promoting bldr job groups

## Source configuration

* `origin`: _Required_ the package origin
* `name`: _Required_ the package name
* `auth_token`: _Optional_ the token to authenticate with the depot. Required when uploading packages.

### Example

```
- name: stable-core-consul-job
  source:
    auth_token: <auth-token>
    name: consul
    origin: core
    type: hab-pkg
resource_types:
- name: hab-pkg
  source:
    repository: eeyun/bldr-resource
    type: docker-image
```

## Behaviour

### `out`: Promotes a bldr job group

### `in`: Get list of all packages in a bldr job group
Will create an object list that consists of all of the packages that have been built in a bldr job group

## Attribution
This resource borrows very very heavily from starkandwayne/habitat-resource
