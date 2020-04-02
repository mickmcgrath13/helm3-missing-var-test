
The follow command outputs all templates.
```
helm \
  upgrade \
  test \
  . \
  --install \
  --dry-run \
  --debug \
  --v="6" \
  -f values-success.yaml
```


The follow command outputs ~no templates~ an error.
```
helm \
  upgrade \
  test \
  . \
  --install \
  --dry-run \
  --debug \
  --v="6" \
  -f values-error.yaml
```

error:
```
Error: template: helm3-missing-var-test/templates/serviceaccount-test.yaml:1:18: executing "helm3-missing-var-test/templates/serviceaccount-test.yaml" at <.Values.test.serviceAccount.enabled>: nil pointer evaluating interface {}.serviceAccount
helm.go:75: [debug] template: helm3-missing-var-test/templates/serviceaccount-test.yaml:1:18: executing "helm3-missing-var-test/templates/serviceaccount-test.yaml" at <.Values.test.serviceAccount.enabled>: nil pointer evaluating interface {}.serviceAccount
```