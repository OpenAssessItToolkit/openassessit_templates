
Manual Test: {{ audit.title|escape }}

{%- if audit.description %}

Description:<br>
{{ audit.description|trim|escape }}

{% endif -%}

__[Please view these simulated screen shots](https://developer.microsoft.com/en-us/microsoft-edge/tools/screenshots/?url={{data.finalUrl|urlencode}})__

__[Current browser market shares](https://www.w3counter.com/globalstats.php)__

Please test in real browsers to ensure the website works on commonly used browsers.  We do not require compatibility with Internet Explorer as it is discontinued. It is up to {{ data.finalUrl|replace('https://', '')|capitalize }} if they wish to spend resources accommodating the obsolete browser.

<br>