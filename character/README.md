# GraphQL: Character by ID

Endpoint: https://rickandmortyapi.com/graphql

Queries in this folder fetch a character by `id` and return `id`, `name`, `status`, `species`, `type`, `gender`.

Example (PowerShell):

```
$Query = Get-Content -Raw -Path .\character-id-1.graphql
$Body = @{ query = $Query } | ConvertTo-Json
Invoke-RestMethod -Uri https://rickandmortyapi.com/graphql -Method Post -ContentType 'application/json' -Body $Body |
  ConvertTo-Json -Depth 5 | Out-File -Encoding UTF8 .\character-id-1-output.json
```

