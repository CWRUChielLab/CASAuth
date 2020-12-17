CASAuth Extension for Mediawiki
===============================
This is compatible with version MediaWiki version 1.33

This differs from the original by offering a new CA Certificate setting that is implemented in the casSetup function.

It also adds a check in casLogin() to see whether a user is already authenticated through another web application before forcing the authentication. This ensures that the phpCAS:getUser() method is able to get the username in the event the user is already authenticated through another session, and prevents the user from needing to log out of their institution's applications before logging into the MediaWiki.

This is forked from the CWRUChielLab/CASAuth repo, both this version and the original seem to be compatible with newer versions of MediaWiki.

Below is the original README content from CWRUChielLab/CASAuth :


Introduction
------------

The CASAuth extension facilitates CAS authentication for your Mediawiki
installation.  This particular code is derived from work found
[here](http://www.mediawiki.org/wiki/Extension:CASAuthentication).

This code is customized towards usage for private wikis, with the ability to
restrict access to the wiki to specific usernames.

This extension is currently written for and tested against Mediawiki 1.27 and
1.23 with phpCAS 1.3.3. However, if you find it works well against a different
version of Mediawiki and/or phpCAS, please feel free to let me know and I will
keep track of it in this README.

Security Update
---------------

To prevent users from logging in as bureaucrats, via specially crafted user
names, be sure to use the latest version of this module, and apply the
suggested change to the `casNameLookup` hook in `CASAuthSettings.php`, as shown
in `CASAuthSettings.php.template`.

Installation
------------

Assuming a working CAS system, installation should take under 15 minutes.
Assume $WIKI is the directory for your wiki.

1.  Create folder $WIKI/extensions/CASAuth/

2.  Download this source code into that directory

3.  Download the [phpCAS](https://wiki.jasig.org/display/CASC/phpCAS) extension
    and extract it to the folder $WIKI/extensions/CASAuth/CAS/

4.  Add the following line to your LocalSettings.php

    ```php
    require_once( "$IP/extensions/CASAuth/CASAuth.php" );
    ```

5.  In the $WIKI/extensions/CASAuth/ directory, copy the
    CASAuthSettings.php.template file to CASAuthSettings.php and modify it for
    your environment.

6.  You should now have working CAS authentication for your wiki!

Credits
-------

Source code found here is derived from the extension found
[here](http://www.mediawiki.org/wiki/Extension:CASAuthentication), originally
written by Ioannis Yessios.
