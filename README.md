Four scripts that test this helm command under different conditions:
```
helm
upgrade \
test \
. \
--install \
--dry-run \
--debug \
--v="6" \
-f ${file}
```

The conditions being tested are:
1. Helm version (3.1.0 vs 3.1.1)
2. Existence of key in values (`values-success.yaml`) vs key missing in values (`values-error.yaml`).

The matrix is as follows:

| Helm Version | Values File | Script | Result |
| ------------ | ----------- | ------ | ------ |
| 3.1.0 | `values-success.yaml` | `./helm3.1.0-success` | Templates **Rendered** |
| 3.1.0 | `values-error.yaml` | `./helm3.1.0-error` | Templates **NOT Rendered!** |
| 3.1.1 | `values-success.yaml` | `./helm3.1.1-success` | Templates **Rendered** |
| 3.1.1 | `values-error.yaml` | `./helm3.1.1-error` | Throws error |