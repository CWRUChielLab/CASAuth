CASAuth(entication) Extension for Mediawiki
===========================================

A CAS Authentication extension for Mediawiki. Tested with versions with
1.19, although it should work for at least versions 1.16+, if not earlier.

Introduction
------------

The CASAuth extension facilitates CAS authentication for your Mediawiki
installation.  This particular code is derived from work found
[here](http://www.mediawiki.org/wiki/Extension:CASAuthentication).

This code is customized towards usage for private wikis, with the ability to
restrict access to the wiki to specific usernames.

This extension is currently written for, and tested against Mediawiki 1.19. 
However, if you find it works well against a different version of Mediawiki,
please feel free to let me know and I will keep track of it in this README.

The extension will follow whatever version of Mediawiki is found in the
[EPEL](http://fedoraproject.org/wiki/EPEL EPEL) repository.

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
