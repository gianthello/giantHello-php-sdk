giantHello PHP SDK
================
The [giantHello Platform][dev] is a set of APIs that make your application more social. Read more about [integrating giantHello with your web site on the giantHello][docs] developer site.

This repository contains the open source PHP SDK that allows you to utilize the above on your website. Except as otherwise noted, the giantHello PHP SDK is licensed under the Apache Licence, Version 2.0 (http://www.apache.org/licenses/LICENSE-2.0.html)

[dev]: http://gianthello.com/developer
[docs]: http://gianthello.com/developer/docs

Usage
-----

    <?php

    require './giatHello.php';

    $facebook = new Facebook(array(
      'appId'  => 'YOUR APP ID',
      'secret' => 'YOUR API SECRET',
      'cookie' => true, // enable optional cookie support
    ));

To make [API][API] calls:

    try {
      $me = $facebook->api('/me');
    } catch (FacebookApiException $e) {
      error_log($e);
    }

Logged in vs Logged out:

    if ($facebook->getSession()) {
      echo '<a href="' . $facebook->getLogoutUrl() . '">Logout</a>';
    } else {
      echo '<a href="' . $facebook->getLoginUrl() . '">Login</a>';
    }

[API]: http://gianthello.com/developer/docs/api/graphapi


Feedback
--------

We are relying on the [GitHub issues tracker][issues] linked from above for
feedback. File bugs or other issues [here][issues].

[issues]: http://github.com/gianthello/giantHello-php-sdk/issues



Tests
-----

In order to keep us nimble and allow us to bring you new functionality, without
compromising on stability, we have ensured full test coverage of the new SDK.
We are including this in the open source repository to assure you of our
commitment to quality, but also with the hopes that you will contribute back to
help keep it stable. The easiest way to do so is to file bugs and include a
test case.