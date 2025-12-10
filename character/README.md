# Character GraphQL queries

This folder contains GraphQL query files and their corresponding JSON responses for individual characters.

Structure

- [character/character-id-1.graphql](character/character-id-1.graphql)
- [character/character-id-1-output.json](character/character-id-1-output.json)
- [character/character-id-2.graphql](character/character-id-2.graphql)
- [character/character-id-2-output.json](character/character-id-2-output.json)
- [character/character-id-3.graphql](character/character-id-3.graphql)
- [character/character-id-3-output.json](character/character-id-3-output.json)
- [character/character-id-4.graphql](character/character-id-4.graphql)
- [character/character-id-4-output.json](character/character-id-4-output.json)
- [character/README.md](character/README.md)

What these files are

- \*.graphql — GraphQL queries that request a character by id:
  - Each query calls `character(id:<N>)` and requests fields: `id`, `name`, `status`, `species`, `type`, `gender`.
- \*-output.json — Captured JSON responses for the corresponding query.

Run a query (example)
Use any GraphQL HTTP client. Example with curl (requests character id 1 and writes JSON output):

```sh
curl -s -X POST https://rickandmortyapi.com/graphql \
  -H "Content-Type: application/json" \
  -d '{"query":"query { character(id:1){ id name status species type gender } }"}' \
  > character/character-id-1-output.json
```

Notes

- Query files are plain GraphQL; you can open them in a GraphQL IDE or send them via any HTTP client.
- Output files reflect the API response shape under the top-level `data` → `character`.
