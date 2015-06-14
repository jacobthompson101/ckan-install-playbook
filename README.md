## README

This is an ansible suite for automatically installing a CKAN data catalogue instance on a freshly provisioned machine. Configuration options need to be filled in before attempting to run these plays, and even then, there's no guarantee they'll work... Some configuration options and code relating to adding plugins providing custom metadata schemas and SSO-functionality ([ckanext-scheming](https://github.com/open-data/ckanext-scheming) and [ckanext-oauth2](https://github.com/conwetlab/ckanext-oauth2), respectively) has been left in, but commented out, in case you would like try them. Getting these to work will take more than uncommenting, though. Kindly refer to the documentation of these plugins.

#### NB!

* This ansible code has been tested (*before the cleaning up the private stuff*) on Ubuntu 14.04 LTS Trusty Tahr ([link to image](http://cloud-images.ubuntu.com/vagrant/#{ubuntu_release}/current/#{ubuntu_release}-server-cloudimg-amd64-vagrant-disk1.box)), with the [CKAN 2.3 release](https://github.com/ckan/ckan/tree/ckan-2.3), or the slightly more recent [City-of-Helsinki fork](https://github.com/City-of-Helsinki/ckan) which fixes a problem with diaeresis (ä, ö, å...). Check the configuration.

* templates/development.ini is an example of a slightly modified CKAN configuration file. There are some cryptographic keys that should be generated by `paster make-config` or filled in by the user: they've been replaced with "FIXME". I've done this because we need to add some lines at specific places in the conf file, which the ansible lineinfile-module isn't great at. You should probably use `paster make-config`. Also the nginx-default configuration file contains a "FIXME".
