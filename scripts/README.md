# Archival scripts

## archive-migration.sh

Migrates the commit history of archived easyconfigs from a local
easybuild-easyconfigs repo to another target repo.

* Archived easyconfigs are taken from the `__archive__` folder in a local
  easybuild-easyconfigs repo

* Migrated easyconfigs are placed in the destination repo keeping the folder
  structure, that is alphabetical directory structure under
  `easybuild/easyconfigs/__archive__`

* Commit history of each migrated file is copied over to destination repo in
  a new branch ready to be PRd

### Requirements

* [bash](https://www.gnu.org/software/bash/) (might work with other Linux shells)
* [Git](https://git-scm.com/)
* [git-filter-repo](https://github.com/newren/git-filter-repo)

### Usage

1. Create an archival branch in an up-to-date `easybuild-easyconfigs` repo

2. Move easyconfigs and any other outdated files into `__archive__` as usual

3. Commit the changes to the archival branch of your local
   `easybuild-easyconfigs` repo

4. Run `archive-migration.sh` using the name of the new archival branch
   (replace `<archival_branch>` in the following) to migrate it into
   `easybuild-easyconfigs-archive`

   a. from dir containing local `easybuild-easyconfigs` and
      `easybuild-easyconfigs-archive` repos:

      ```
      $ ./easybuild-easyconfigs-archive/scripts/archive-migration.sh <archival_branch>
      ```

   b. from top dir of local `easybuild-easyconfigs-archive` repo:

      ```
      $ ./scripts/archive-migration.sh -a . -e /path/to/easybuild-easyconfigs <archival_branch>
      ```

