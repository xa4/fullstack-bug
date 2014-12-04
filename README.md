fullstack-bug
=============

I came accross a very weird bug in node, express, or something else pulled by angular-fullstack.
The code is supposed to serve a long string (>50k). The bug does not occur with small strings.
When reading the api that returns this long string, browsers duplicate the string.
It occurs with chrome, after a hard reload.
It occurs with safari, everytime
It occurs with firefox, everytime
It does not occur with curl.

How to reproduce
----------------

Scaffold a basic fullstack app:

    yo angular-fullstack
    
using the following options (no mongodb)
https://github.com/xa4/fullstack-bug/blob/master/.yo-rc.json

Add the long string serving api, such as https://github.com/xa4/fullstack-bug/commit/1e8e81c9fa364871e69ef611ae189b00d3ee452a

Start your server

    grunt serve:dev

Browse to http://localhost:9000/api/things

Hit reload. Search for the string "test". If it appears twice, the bug appears. If it does not, try to hard-reload the page,
and search for "test" again.

Remarks:
I'm using node v0.10.33 on OSX Yosemite.
