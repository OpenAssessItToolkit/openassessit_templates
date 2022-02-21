<details>
<summary>_Other options:_</summary>
{{ item.node.explanation|escape|replace('  ', '<br>') }}
</details>

<details>
<summary>_Additional debugging details_</summary>
Path:<br>
`{{ item.node.path }}`<br>
Selector:<br>
`{{ item.node.lHId|replace('$', 'S') }}`
</details>