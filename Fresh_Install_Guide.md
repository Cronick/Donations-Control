# Fresh Install
There are certain requirements that must be met for Donations Control to work.

* Donors must be assigned custom flags from SourceBans
* You must be using groups, to assign server access and perks to donors. 'Server Admin Groups' and 'Server Groups' are the ones needed. 'Web Admin Groups' are not used by Donations Control.
* You have access to some sort of crontab.
* Once you have your SourceBans installation configured correctly, you should begin by importing install.sql (located in sql/install.sql) to your database. This will create all the tables needed. After you have completed that delete the whole install folder. Then head on to includes/config.php and fill it out.

## How to set the groups

* Log into the admin panel of Sourcebans.
* Go to the 'admins' tab, and hit 'Add new admin'.
* fill out the 'Admin Details' like so.
  * Admin Login: TESTDONOR
  * Admin Steam ID: STEAM_0:1:111111 (use STEAM_0:2:222222 for the seconds group, 333 for 3 ect.)
  * 'Admin Email','Admin Password','Server password': leave blank.
  * Server Access: Select the server group you want your first donor tier to have access to.
  * Server Admin Group: Select the donor group you setup here.
  * Web Admin Group: set to 'No Permissions'
* Log into https://YOURDOMAIN.com/donations/admin with your Sourcebans user/pass.
* Go strait to the groups menu
* Enter STEAM_0:1:111111 in the 'Add new group' section, and fill out the other inputs to your liking.
* Hit add new group
* Do the same for the other Steam IDs you set in soucebans
* Once your finished, delete the test users from sourcebans.
Set your crontab to call scripts/remove_expired.php daily. Something like this will do "@daily wget http://mydomain.com/scripts/remove_expired.php"
