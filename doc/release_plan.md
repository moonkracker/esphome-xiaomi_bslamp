# Release plan

**All development is done in the `dev` branch**

$ git checkout dev

Once the development branch is ready for a new production release, the following
steps are followed:

**Update the CHANGELOG.md**

Make sure all notable changes are recorded in the changelog.

**Update ESPHome version information**

The minimum ESPHome version requirement must be documented correctly in the following files:

  * doc/installation.md (at the start of the file)
  * README.md (at the start of the quick start guide)
  * CHANGELOG.md (at the start of the log for the released version)
  * `components/xiaomi_bslamp2/__init__.py` in the function
    `check_version_compatibility()`. This function can also be used
    to check the maximum version of ESPHome that can be used. An example
    of this use can be found in the `release/2021.10.0` branch.

**Push the dev changes to GitHub**

$ git add ...
$ git commit -m "Prepare for release"
$ git push

**Create version release branch**

Branch `dev` to a `release/<version>` branch, e.g. `release/2021.10.0`.
```
$ git checkout -b release/2021.10.0
```

**Update project version information**

The version of this project (e.g. `2021.10.0`) must be updated in:

  * `example.yaml` (the `ref:` for the bslamp2 configuration package)
  * `packages/core.yaml` (the `ref:` for the external component)

**Push the release to GitHub**

```
$ git push --set-upstream origin release/2021.10.0
```
