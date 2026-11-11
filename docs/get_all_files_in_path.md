# Files used by a merged config

The API does not expose `/v1/list_files`. To find the files used to resolve a
configuration, request the merged config and read `config.override_stack`.

```http
GET /v1/configs/software_a?hostname=w10dt000001&subject_id=614173
```

The response contains `config.data` and `config.override_stack`. The stack lists
the selected files from defaults through the requested scopes in merge order.
