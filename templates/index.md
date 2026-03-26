# {{ data.requestedUrl|replace('https://', '')|capitalize }} Assessment

__<{{ data.requestedUrl }}>__

__Screenshot:__

![Screenshot of this website](assets/{{ generate_img_filename(data.finalUrl, 'cat', '_screenshot_') }})

<div id="toc">
<!--TOC-->
</div>

{% for cat_id, cat in data.categories.items() -%}

<br>
<hr>

# {{ cat.title }}

{{ cat.description }}

{{ cat.manualDescription }}

Below are opportunities to improve the accessibility and compliance of this website. Web accessibility assessments include tools like [WAVE](https://chromewebstore.google.com/detail/wave-evaluation-tool/jbbplnpkjmmeebjpijfedlgcdilocofh) and [Deque Axe Dev Tools](https://chromewebstore.google.com/detail/axe-devtools-web-accessib/lhdoppojpmngadmnindnejefpokejbdd). We also do manual accessibility tests with keyboard navigation and screen reader software compatibility which can be found in this [video series on web accessibility assessments](https://www.youtube.com/playlist?list=PLF4_5fOOz5tlYmG6BnX8q_ILEzBPNrDbK).

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
