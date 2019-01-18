<style>
img { max-width:500px; height: auto; max-height: 500px; min-width:10px; min-height:10px; }
img,iframe {border: 1px solid #ccc;}
a { color: blue; }
pre code { font: 9px; }
pre { font: inherit; word-wrap: break-word; background: none; border: none; }
.force-thumbnail { width: 150px; }
.force-thumbnail img { height: auto; }
</style>

# {{ data.requestedUrl|replace('https://', '')|capitalize }} Assessment

__<{{ data.requestedUrl }}>__

__Screenshot:__

![Screenshot of this website](assets/screenshot.png)

{% for cat_id, cat in data.categories.items() -%}
# {{ cat.title }}
{{ cat.description }}
{% for audit in cat.sorted_audits %}

{%- if ( audit.scoreDisplayMode == "binary" and audit.score == 0) or
        (audit.scoreDisplayMode == "numeric" and audit.score != 100 ) or
        (audit.scoreDisplayMode == "manual") or
        (audit.scoreDisplayMode == "informative") or
        (audit.scoreDisplayMode == "error")
%}
##{{ audit.title }}
{%- include [audit.audit_template, "audit_result.md"] %}
<hr>
<br>
{%- endif %}

{% endfor %}
{%- endfor -%}

{% include 'includes/footer.md' %}
