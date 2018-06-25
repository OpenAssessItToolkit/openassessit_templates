<style>
img { max-width:400px; height: auto;}
img,iframe {border: 1px solid #ccc;}
a { color: blue; }
pre code { font: 9px; }
pre { font: inherit; word-wrap: break-word; background: none; border: none; }
.force-thumbnail { width: 150px; }
.force-thumbnail img { height: auto; }
</style>

# {{ data.requestedUrl|replace('https://', '')|capitalize }} Assessment

__{{ data.requestedUrl }}__

__Screenshot:__

{# TODO: automate creating a single screenshot by writing custom audit based off of Performance audit lighthouse-core/audits/metrics.js using emulation: desktop #}

![Screenshot of this website](http://via.placeholder.com/480x300)

{% for cat_id, cat in data.categories.items() -%}
# {{ cat.title }}
{% for audit_id, audit in cat.audits.items() %}

{%- if ( audit.scoreDisplayMode == "binary" and audit.score == 0) or
        (audit.scoreDisplayMode == "numeric" and audit.score != 100 ) or
        (audit.scoreDisplayMode == "manual") or
        (audit.scoreDisplayMode == "informative") or
        (audit.scoreDisplayMode == "error")
%}

<br>

## {{ audit.title }}
{%- include [audit.audit_template, "audit_result.md"] %}
{%- endif %}

{% endfor %}
{%- endfor -%}
