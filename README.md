# Instana Gem Version Resource

This [Concourse](https://concourse-ci.org/) resource allows you to track the version of a Ruby Gem on [RubyGems.org](https://rubygems.org).

## Source Configuration

* `gem`: *Required.* The name of the gem to follow.

### Example

``` yaml
resource_types:

  - name: gem-version
    type: registry-image
    source:
      repository: instana/gem-version-resource
      tag: latest

resources:

  - name: instana-gem-version
    type: gem-version
    source:
      name: instana
```

## Behaviour

### In

No additional parameters are supported.
The `version` file will be populated with the latest version.

## Support

To ensure we do not miss your requests, we disabled the Issues functionality for this repository.
If you have questions about how to use Concourse resource, please open a [support request](https://support.instana.com/hc/en-us/requests/new).

## Development

The actions of the resource are written in `bash`, `curl` and `jq`, with the goal of being easy to debug in local even from inside a Docker image (hello, [`fly intercept`](https://concourse-ci.org/builds.html#fly-intercept)!).
The test scripts assumes a local Docker daemon.

## Build

```sh
docker build . -t instana/gem-version-resource
```

## Contributing

Ah, our kind of person!
Go ahead, open a Pull Request.

Please be aware that we will be able to accept only code contributed under the Apache 2.0 license.
