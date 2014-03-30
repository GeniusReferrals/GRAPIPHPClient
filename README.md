PHPClient
=========

# Installing Genius Referral PHP API via Composer

The recommended way to install Genius Referral PHP API is through Composer.

# Install Composer
curl -sS https://getcomposer.org/installer | php

# Add Genius Referral PHP API as a dependency
php composer.phar require geniusreferrals/genius-api-php-client:~0.1

After installing, you need to require Composer's autoloader:

require_once '../vendor/autoload.php';

# Using Genius Referral PHP API

<?php

require_once '../vendor/autoload.php';

use GeniusAPI\GRPHPAPIClient;

// Create a new GRPHPAPIClient object
$objGeniusApiClient = new GRPHPAPIClient('client1@mail.com', '3433148');

// Get the list of Genius Referrals client accounts
$strResponse = objGeniusApiClient->getAccounts();

// Get the response code from the previous request
$intResponseCode = objGeniusApiClient->getResponseCode();

 
# Unit testing
Genius Referral PHP API uses PHPUnit for unit testing. In order to run the unit tests, you'll first need to install the dependencies of the project using Composer: php composer.phar install --dev. 

You can then run the tests using using the following command at the project root:
phpunit -c vendor/geniusreferrals/genius-api-php-client/

If you are running the tests with xdebug enabled, you may encounter the following issue: 'Fatal error: Maximum function nesting level of '100' reached, aborting!'. This can be resolved by adding 'xdebug.max_nesting_level = 200' to your php.ini file.
