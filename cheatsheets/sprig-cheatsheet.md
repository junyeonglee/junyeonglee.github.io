# Sprig

Most common `sprig` pipeline

```sh
value | default default_value
value | quote
value | upper
value | trunc 63
value | trimSuffix "-"
value | b64enc
value | randAlphaNum 10
value | toYaml
list value ... | join "-"
```
