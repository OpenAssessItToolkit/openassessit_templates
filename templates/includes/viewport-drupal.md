Option 1:

Check if you can change this using the GUI provided by your Drupal Theme. Optionally, you should re-export the theme settings so the .info file stays up to date.

Option 2:

In your Drupal sub-theme this can also be done in the template.php file with something similar to this (‘alpha-viewport’ $head_element name varies depending on the base theme):

$head_elements['alpha-viewport'] = array(
  '#type' => 'html_tag',
  '#tag' => 'meta',
  '#attributes' => array(
    'name' => 'viewport',
    'content' => 'width=device-width, initial-scale=1, maximum-scale=5, minimum-scale=1, user-scalable=yes',
  ),
);

Option 3:

Go into the html.tpl.php file in the sub-theme and change it there.

Changing the maximum scale to 5 will allow people to scale the page. Depending on how the website is styled, it could cause unexpected issues with the mobile view of the site getting a horizontal scrollbar. It is worth testing to ensure that does not happen.

<meta name="viewport" content="width=device-width, initial-scale=1, maximum-scale=5" user-scalable="yes">