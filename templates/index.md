# {{ data.requestedUrl|replace('https://', '')|capitalize }} Assessment

__<{{ data.requestedUrl }}>__

__Screenshot:__

![Screenshot of this website](assets/{{ generate_img_filename(data.finalUrl, '_screenshot_') }})

<div id="toc">
<!--TOC-->
</div>

{% for cat_id, cat in data.categories.items() -%}

<br>
<hr>

# {{ cat.title }}

{{ cat.description }}

{{ cat.manualDescription }}

{% for audit in cat.sorted_audits %}
{%- if ( audit.scoreDisplayMode == "binary" and audit.score == 0) or
        (audit.scoreDisplayMode == "numeric" and audit.score != 100 ) or
        (audit.scoreDisplayMode == "manual") or
        (audit.scoreDisplayMode == "informative") or
        (audit.scoreDisplayMode == "error")
%}

{% include [audit.audit_template, "audit_result.md"] %}

{% endif %}

{% endfor %}
{% endfor -%}

{% include 'includes/footer.md' %}
