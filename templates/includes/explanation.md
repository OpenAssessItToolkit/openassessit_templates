{{ item.node.explanation|escape|replace('  ', '<br>') }}

<details>
<summary>_Additional debugging details_</summary>
Path:<br>
`{{ item.node.path }}`<br>
Selector:<br>
`{{ item.node.selector|replace('$', 'S') }}`
</details>