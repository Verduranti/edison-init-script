Init.d script for starting bleno on Edison
=======================================================

A specific example of an init script that works on Edison

This example starts the [Bleno](https://github.com/sandeepmistry/bleno) NodeJS
script that broadcasts Bluetooth LE services offered by my edison.
This example uses my custom demo.js script, but any of the scripts will work.

Also includes the killing of bluetoothd currently required.
Please remove this if that issue if gets worked out


Getting started
---------------

Copy _bleno_ to /etc/init.d and rename it if you need to.

Notes about the three variables that need to be set in the script:

### dir ###

This is wherever bleno is installed. If you followed the bleno getting 
started guide you won't need to change this.

### user ###

Not used unless you play with your Edison as something other than root.

### cmd ###

The command line to start the process.

Script usage
------------

### Start ###

Starts the app.

    /etc/init.d/algorithms start

### Stop ###

Stops the app.

    /etc/init.d/algorithms stop

### Restart ###

Restarts the app.

    /etc/init.d/algorithms restart

### Status ###

Tells you whether the app is running. Exits with _0_ if it is and _1_
otherwise.

    /etc/init.d/algorithms status
    
Running at startup
------------------

After you've set everything up and tested with the above commands you need 
to do one more thing to add it to the list of things run on startup.
Run the following command in an Edison terminal window:

    update-rc.d bleno defaults

If you change the file name from bleno to something else you will need to 
change the above command as well.

Logging
-------

By default, standard output goes to _/var/log/scriptname.log_ and
error output to _/var/log/scriptname.err_. If you're not happy with
that, change the variables `stdout_log` and `stderr_log`.

License
-------

Copyright (C) 2012-2014 Felix H. Dahlke

This is open source software, licensed under the MIT License. See the
file LICENSE for details.
