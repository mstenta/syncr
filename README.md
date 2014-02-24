syncr
=====

Syncr is a script for making rsync easier.

It will prompt you for all the necessary information, assemble the rsync call, and execute it.

Supported options:

* Source
* Destination
* Timestamp preservation
* Permission preservation
* Executability preservation
* Exclude certain files (uses list in provided excludes.txt)
* Delete destination files that aren't in the source
* Preview the rsync command before executing

Example command usage:
----------------------

    >> syncr
    Source (include trailing slash): [./]
    Destination (no trailing slash): ./test
    Should file timestamps be preserved? [Y/n]: y
    Should file permissions be preserved? [Y/n]: y
    Should file executability be preserved? [Y/n]: y
    Should files be excluded from excludes.txt? [Y/n]: y
    Delete files from the destination if they are not in the source? [y/N]: n

    The following rsync command will be executed:

        rsync -vv --stats --progress -rlxtpE --exclude-from excludes.txt ./ ./test

    Are you sure you want to continue? [y/N]: y
