This roadmap pertains to the entire Wren Security organization, and covers all of the projects we maintain.

## Phase 0. Prepare Contributor Guidelines _(Done)_
The common documents for open-source projects need to be set up for both Wren Security in general, and for each project. This includes the Contributor Guidelines, Code of Conduct, READMEs, and others.

Documents that have been created:
* Contributor Guidelines
* Code of Conduct
* Branching Guidelines
* Project README (skeleton)
* Project ROADMAP (skeleton)
* Project CONTRIBUTORS (skeleton)

## Phase 1. Get All Stable, Major Release Versions to a Buildable State _(PRs available; almost complete)_
The last stable major and minor release of each project that ForgeRock had publicly released under open source licenses must be brought to a buildable state. This includes:

* OpenDJ 3.0
* OpenAM 13.0, OpenAM 13.5
* OpenIDM 4.0

At first, this includes just using the [wrensec-deps](/WrenSecurity/wrensec-deps) repository and installing the dependencies straight into the local Maven repository. Later, this must be accomplished by:

1. Setting up `sustaining/` branches for these versions according to Wren Security [branch conventions](/WrenSecurity/wrensec-docs/wiki/Versioning,-Branching,-and-Tagging#branching). _(Done)_
2. Updating the POM files of each top-level project and its dependencies to source from Wren Security repositories and no longer source from `maven.forgerock.org`. _(Done)_
3. Setting up a GPG whitelist and configuring builds to verify GPG signatures (to ensure all dependencies come from authentic sources) (complete).
4. Building and publishing all of the dependencies of these projects to the [Wren Security JFrog repository](https://wrensecurity.jfrog.io/wrensecurity/webapp/). _(Done)_
5. ~~Archiving ForgeRock binaries &ndash; from smaller projects that are not (yet) available to be built from source &ndash; in the ForgeRock archive of [the Wren Security BinTray repository](https://bintray.com/wrensecurity/forgerock-archive).~~
6. GPG signing all binaries in all repositories. _(Done)_
7. Tagging and releasing these versions on GitHub.

## Phase 1.5 Get All Subscription Maintenance Release Versions to a Buildable State _(PRs available; almost complete)_
For some projects, Wren Security has access to the last available CDDL-licensed package from ForgeRock that was previously provided only to Backstage subscribers. During this phase, this code must be brought to a buildable state. This includes:
* OpenDJ 3.5.1
* OpenAM 13.5.1

This must be accomplished by:
1. Committing the code to new branches in GIT source control (backstage downloads lack Git history), on new `sustaining/` branches according to Wren Security [branch conventions](/WrenSecurity/wrensec-docs/wiki/Versioning,-Branching,-and-Tagging#branching). _(Done)_
2. Applying all of the same project build changes from Phase 1 to POM files and dependencies introduced by the new code. _(Done)_
3. Updating the GPG whitelist to include the dependencies needed by the new code. _(Done)_
4. Building and publishing all of the dependencies of these projects to the [Wren Security JFrog repository](https://wrensecurity.jfrog.io/wrensecurity/webapp/). _(Done)_
5. Tagging and releasing these versions on GitHub.

## Phase 2. Get All Unstable Release Branches Buildable  _(PRs available; work in progress)_
The bleeding-edge, pre-release development snapshots (i.e. `master` branch) of each project that ForgeRock had publicly released under open source licenses must be brought to a buildable state. This includes:

* OpenDJ 4.0 (DS 5.x)
* OpenAM 14.0 (AM 14.x)
* OpenIDM 5.5 (IDM 5.5) _(Done)_

This must be accomplished by:
1. Applying all of the same project build changes from Phase 1 to POM files and dependencies of the bleeding edge `master` branches introduced by the new code. _(Done)_
2. Tracking down, replacing, or reconstituting dependencies & build artifacts that Wren Security does not have readily available in source control (typically, these are versions of artifacts that were only briefly available before ForgeRock cut-off trunk source code access). _(Almost done)_
3. Updating the GPG whitelist to include the dependencies needed by the new artifacts. _(Done)_
4. Building and publishing all of the dependencies of these projects to the [Wren Security JFrog repository](https://wrensecurity.jfrog.io/wrensecurity/webapp/).

## Phase 3. Build Up Backlog _(On-going)_
A backlog of issues and feature requests for the projects needs to be created. All the issues and requests that people keep in different places should be submitted as issues to the GitHub projects, so that they can be worked on publicly.

## Phase 4. Set up Projects for Continuous Integration _(50% Complete)_
- Automatic CI builds triggered from Wren Security project branches must be setup in order to ensure that breaking changes are caught immediately. _(Done)_
- The results of builds must be integrated into the pull request process to ensure that maintainers are merging seemingly-stable code into `master` and release branches.  _(Done)_
- Automatic code style checks are added during the CI and/or pull request process to enforce project style guidelines without maintainers having to manually provide style critiques in pull requests. _(Not Started)_
- Builds must be configured to publish `SNAPSHOT` and release artifacts to the [Wren Security JFrog repository](https://wrensecurity.jfrog.io/wrensecurity/webapp/). _(Not Started)_

## Phase 5. Prepare Projects for Further Advancement _(Started)_
There are several steps to this stage:
1. Security patches must be prepared for all know security defects in the release versions Wren Security maintains. _(Started)_
2. Licensed and legally problematic files need to be either replaced or removed. _(Started)_
3. ~~Dependencies archived in the [the Wren Security BinTray repository](https://bintray.com/wrensecurity/forgerock-archive) for which no source code is available need to be cataloged, so that they can be replaced by new artifacts built from source in the not-to-distant future.~~
4. The Maven group ids of all projects needs to be changed to `org.wrensecurity`. _(Not Started)_

## Phase 6. Write New Project Documentation to Replace Original ForgeRock Documentation _(Started)_
Because all of ForgeRock's original documentation is licensed under the Creative Commons Non-Commercial, No Derivatives license (CC BY-NC-ND), we need to create our own from scratch. This includes references, tutorials, samples, and such.