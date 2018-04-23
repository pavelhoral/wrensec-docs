## Versioning
* All projects follow the [standard Maven versioning scheme](https://docs.oracle.com/middleware/1212/core/MAVEN/maven_version.htm#MAVEN8855).
* Re-releases of ForgeRock's versions have the same version as the original ForgeRock artifact, so that legacy code can still be built without maintainers having to sort through build issues and upgrade all legacy projects to work with newer artifact versions.
* New release versions start from one version higher than the last ForgeRock version. For example:
  * A patch version of `3.5.2` if the last FR patch version was `3.5.1`.
  * A minor version of `3.6` if the last FR minor version was `3.5.x`.
  * A major version of `4.0` if the last FR major version was `3.x`.

## Branching
All Wren Security projects follow the [GitLab scheme](https://about.gitlab.com/2014/09/29/gitlab-flow/) for branching.

There are three types of branches:
- `master`
- `sustaining/___`
- `feature/___`

## `master` Branch
* Contains the latest, bleeding-edge code that may not yet be suitable for production use.
* All new features are merged here first (as described below).

### `sustaining/` Branches
* Each branch should be cut from / be based off the `master` branch at the time that work to prepare new minor or major release begins.
* The name of each branch should be `sustaining/<major>.<minor>.x`.
* Each branch contains a stable minor versions of the project.
* After branching off of `master`, only serious, version-specific bug fixes are addressed in the branch. _(Release blockers must be treated as new features that are merged into `master` and then cherry-picked into the release)._
* At all times other than during a release, the patch version on the `sustaining/` branch should be a `SNAPSHOT` version, such as `<major>.<minor>.<patch>-SNAPSHOT`. During the release process, the patch version needs to be incremented to the final, non-SNAPSHOT version, tagged, and then incremented to the next SNAPSHOT patch version (e.g. `3.5.1-SNAPSHOT` goes to `3.5.1`, gets tagged and packaged, and then the branch gets incremented to `3.5.2-SNAPSHOT`).
* Patch versions on these branches are handled with tags.
* Once a version is no longer supported, its sustaining branch is deleted.

## `feature/` Branches
* Each branch contains a new feature or major bug fix that is being actively developed.
* Most contributors should fork Wren's main repository and create their feature branches within their fork, rather than creating feature branches directly in Wren's copy, unless multiple contributors are collaborating on a large feature that has the blessing of the project maintainers.
* New feature branches should start from / be created off of the latest from `master` before work on the feature begins.
* Each new feature must first be merged into the `master` branch, via a Pull Request. From `master`, these new features can then be cherry-picked into maintenance / release branches, as required.
* Feature branches are deleted after the Pull Request that merges them into `master` has been accepted.

# Tagging
## Release Tags
* As mentioned previously, when work on a particular minor version or patch version is complete, the commit that finalizes the Maven version (i.e. the commit that changes the version number from `<major>.<minor>.<patch>-SNAPSHOT` to `<major>.<minor>.<patch>`) an annotated tag must be created that points to that commit.
* The tag should be named `<major>.<minor>.<patch>`, according to the major, minor, and patch components of the version number, respectively.
* **The release commit must be GPG signed by the release manager.**
* A GitHub release for the tag must be created in GitHub, and the description of the release should include or link to the CHANGELOG for that version.

## Legacy Branches & Tags
* All original version tags inherited from ForgeRock are re-tagged (with lightweight tags) named `forgerock/X/Y/Z`, where `X/Y/Z` is the original name of ForgeRock tag. This helps us clearly differentiate Wren's tagged releases from ForgeRock's original version tags.
* Any tags that already contain `forgerock` or the project name in the tag are sanitized to remove the prefix (e.g. `forgerock-parent/1.0.2` becomes `forgerock/1.0.2`; `forgerock/1.3` becomes `forgerock/1.3`).  
* Any original branches inherited from ForgeRock are converted over to lightweight tags named `forgerock/X/Y/Z`, where `X/Y/Z` is the original name of the branch from ForgeRock (e.g. `release/4.0` becomes `forgerock/release/4.0`). This provides a reference point for old code versions inherited from ForgeRock, without cluttering up our projects with stale branches.
* The original tags and branches are deleted.