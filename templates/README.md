# Lighthouse to Markdown Templates

For use with https://github.com/ihadgraft/lighthouse-reporter


This script runs [lighthouse](https://developers.google.com/web/tools/lighthouse/) and provides the result to a primitive markdown templating system.

## Installation

Put these templates in the root of lighthouse-reporter in a `/user/templates` folder.

## Overriding templates

This format is meant to be used with the online markdown editor https://pandao.github.io/editor.md/en.html or the MacDown app https://macdown.uranusjr.com/. Both of them can export the MD as HTML.

My templates are opinionated. My workflow:

1. Run lighthouse and generate a JSON file.
2. Use lighthouse-reporter to consume and generate the Markdown files.
3. Augment Markdown file with specific simple help text and advice for this client.
4. Post screenshots of the visual location of the errors.
5. Export as HTML.
6. Post on github.io to share with clients.

If you do not like this format you can make your own.
