# Set of tools used to create Centreon Debian packages

# build-all

With this script you can build all debian packages.

Simply run from an empty directory:

	curl https://raw.githubusercontent.com/centreon-deb/tools/build-all | sh

# import-from-tgz

This script imports PHP history from [PEAR](https://pear.php.net/) to
current git repository. All data are in `import-from-tgz.d/*` files. Each data file is a
bash stanza defining:

* `PACKAGE`: the pear name of the package (such as `DB_DataObject`)
* `VERSIONS`: A list of all releases. Each release have the version number
  as first field and release date after (such as `0.2 2002-07-12 05:07
  UTC`). This list must be in reverse order.

## Usage

Create an empty pear branch:

	git checkout master
	git branch -D pear
	git checkout --orphan pear
	git reset --hard

Run `import-from-tgz` script from the git repository:

	/path/to/import-from-tgz /path/to/import-from-tgz.d/php-log

Optionally you can rename `pear` branch to `master`. Beware that your master
branch would be destroyed:

	git branch -D master
	git branch -m pear master

# Copyright

Copyright © 2016 Sébastien Gross \<seb•ɑƬ•chezwam•ɖɵʈ•org\>.

Released under WTFPL (http://sam.zoy.org/wtfpl/COPYING).

Feel free to contact me if you want to participate.

Follow me on twitter https://twitter.com/renard_0
