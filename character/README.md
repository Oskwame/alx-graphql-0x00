# GraphQL: Character Queries

Endpoint: https://rickandmortyapi.com/graphql

Single character by `id`: `id`, `name`, `status`, `species`, `type`, `gender`.

```
$Query = "query { character(id: 1) { id name status species type gender } }"
Invoke-RestMethod -Uri https://rickandmortyapi.com/graphql -Method Post -ContentType 'application/json' -Body (@{ query = $Query } | ConvertTo-Json) |
  ConvertTo-Json -Depth 5 | Out-File -Encoding UTF8 .\character-id-1-output.json
```

Paginated characters (pages 1–4): select `id`, `name`, `status`, `image` from `results`.

```
$Query = "query { characters(page: 1) { results { id name status image } } }"
Invoke-RestMethod -Uri https://rickandmortyapi.com/graphql -Method Post -ContentType 'application/json' -Body (@{ query = $Query } | ConvertTo-Json) |
  ConvertTo-Json -Depth 5 | Out-File -Encoding UTF8 .\characters-page-1-output.json
```

