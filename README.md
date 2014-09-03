# OpenTok CakePHP 2.x Sample

This repository is just a proof of concept for using OpenTok with CakePHP 2.x

This project uses the [Advanced Installation with Composer](http://book.cakephp.org/2.0/en/installation/advanced-installation.html#installing-cakephp-with-composer)
section of the guide to get started. Beyond those instructions all thats been done is to add a route
(Config/routes.php), add the `opentok()` method to the PagesController
(Controller/PagesController.php), and add corresponding view (View/Pages/opentok.ctp).

## Set up

1. Copy the file `Config/opentok.php.default` to `Config/opentok.php` and edit the file to include
   your own API Key and API Secret.
1. Run `composer install` to install the required dependencies.
1. Set your webserver (such as Apache or nginx) to point to the `webroot/` directory. Check the
   [documentation](http://book.cakephp.org/2.0/en/installation/url-rewriting.html) if you need more
   help with this step.

## Usage

Once you have the project set up, visit the `/opentok` path for the application. It will print out
a new Session ID and Token, which were generated on the server and can be used to connect. You may
safely ignore any warnings that appear related to opening `Config/database.php`.

**Note**: This example intentionally leaves out setting up a database to store Session IDs and
loading the JavaScript library to connect to the Session. Its just a simple proof of concept that
the OpenTok PHP SDK is in fact compatible with CakePHP 2.x.

## Ideas

If you'd like to further develop this example, feel free to fork and send a Pull Request. You could
start by adding a database, storing the generated sessions and allowing users to actually connect,
publish, and subscribe to those sessions. CakePHP also provides a Plugin architecture, so it would
be interesting to explore how the OpenTok PHP SDK could be encapsulated as a Plugin.
