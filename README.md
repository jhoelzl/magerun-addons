MageRun Addons
==============

Some additional commands for the excellent [N98-MageRun](https://github.com/netz98/n98-magerun) Magento command-line tool.

Installation
------------
There are a few options.  You can check out the different options in the [MageRun
docs](http://magerun.net/introducting-the-new-n98-magerun-module-system/).

Here's the easiest:

1. Create ~/.n98-magerun/modules/ if it doesn't already exist.

        mkdir -p ~/.n98-magerun/modules/

2. Clone the magerun-addons repository in there

        cd ~/.n98-magerun/modules/ && git clone https://github.com/jhoelzl/magerun-addons

3. It should be installed. To see that it was installed, check to see if one of the new commands is in there, like `customer:clean-address-vat-id`.

        n98-magerun.phar customer:clean-address-vat-id

Commands
--------

    
### Clean up customers' address VAT-ID field ###

A large number of customers enter their Tax/VAT number incorrectly. Common mistakes are using dots and/or spaces. This command loops through the taxvat fields already in the database and cleans them up. So 'nl 01.23.45.67 b01' (which won't validate) will become 'NL01234567B01' (which will validate). This is useful for future purchases by these customers.

    $ n98-magerun.phar customer:clean-address-vat-id
    
    
Credits due where credits due
--------

The command is based on https://github.com/peterjaap/magerun-addons and modified a little bit to work with VAT field on mysql table customer_address_entity_varchar instead of customer_entity_varchar.
