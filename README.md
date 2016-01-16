Kohana 3.2 client library for the MailChimp API v2.0 

Forked and modified from https://github.com/drewm/mailchimp-api/ to provide for Mailchimp API library

#Installation

Place it in the modules folder and enable it in bootstrap.

Examples
--------
Basic usage
	<?php
	$MailChimp = new Mailchimp('abc123abc123abc123abc123abc123-us1'); // where 'abc123abc123abc123abc123abc123-us1' is your API key
	?>

List lists (lists/list method)

	<?php
	$MailChimp = new Mailchimp('abc123abc123abc123abc123abc123-us1');
	print_r($MailChimp->call('lists/list'));
	?>

Subscribe someone to a list

	<?php
	$MailChimp = new Mailchimp('abc123abc123abc123abc123abc123-us1');
	$result = $MailChimp->call('lists/subscribe', array(
					'id'                => 'b1234346',
					'email'             => array('email'=>'test@testdomain.com'),
					'merge_vars'        => array('FNAME'=>'Rick', 'LNAME'=>'Sanchez'),
					'double_optin'      => false,
					'update_existing'   => true,
					'replace_interests' => false,
					'send_welcome'      => false,
				));
	print_r($result);
	?>
For further usages see official documentation for MailChimp API here https://apidocs.mailchimp.com/