# SHIELD BOSH Backup / Restore Add-on

This BOSH release provides add-on tools for augmenting SHIELD
Agents with Pivotal's BBR toolchain for integrating with
BOSH deployments.

## Versions

The original project maintainers (Stark & Wayne) do not actively maintain it anymore, so forked it and built a new release.
The following `BBR` version is available from this repo:

 - **1.9.36** via `shield-addon-bbr`

Need a version we don't (yet) support?  Open a [Github Issue][bug]
asking that we package it up.  Please identify the full version
and a link to the canonical download page.

## Using this BOSH Release

**Note:** This BOSH release is not intended to stand on its own.
It exists to augment the `shield-agent` job of the [SHIELD BOSH
Release][owner], and only in cases where the bbr utilities are
missing.

To colocate this specific `v0.2.2` BOSH release with your shield-agent instance
group, just add a new job to the group:

```yaml
instance_groups:
  - name: whatever
    jobs:
      # ...
      - name:    shield-addon-bbr
        release: shield-addon-bbr

releases:
  # ...  
  - name: shield-addon-bbr    
    sha1: 1448fe17c455a817cc07a8fb6f6758eb6d7f9267
    url: https://github.com/rwsgithubcf/shield-addon-bbr-boshrelease/raw/master/releases/download/v0.2.2/shield-addon-bbr-0.2.2.tgz    
    version: 0.2.2
```

That's really all there is to it.

[bug]: https://github.com/shieldproject/shield-addon-bbr-boshrelease/issues
[owner]:   https://github.com/starkandwayne/shield-boshrelease
