# PV Lists
This plugin provides lists for administration of members and orders. It also provides a listing of recipes with hyperlinks to the reciped selected.

## Activation
The plugin is recognised by WordPress through the header in index.php.
The plugin tests to ensure it is not being run outside WordPress. Supporting files are included. 
Activation is through the register_activation_hook, which calls the function pv_activate_plugin that is contained in the activate.php file located in the includes folder. Activation checks that the WordPress version is 5.0 or higher.

## De-activation
No specific action is taken or required.

## Operation
Shortcodes are added through index.php and are used to initiate action.

### Initiation
A separate shortcode is available to call individual reports. Each shortcode is defined in a separate file in the folder includes/shortcodes. The plugin contains shortcodes for Orders and Members as well as a test function. Shortcodes used:
- [order-list] returns a listing of recent orders
- [member-list] returns a listing of all members
- [recipes-list] returns a listing of all recipes

### Database query
Each SQL query is contained in its individual function file located in the includes folder. The function tests that the current user is logged in and aborts if necessary. The SQL query is executed and the results passed as an object to the function display_table().

### Formated output
The function display_table parses the object in a nested loop. The outer loop steps through the rows of the table and the inner loop steps through the column values. The result is output directly to screen.

### Download outputs
the function convert_to_csv provides a download file in comma delimited format.

## Revision History
1.5 Recipe lists added.
1.6 Order list query modified to recognise if order was fully processed or cancelled.
1.7 Order list query modified to recognise versions