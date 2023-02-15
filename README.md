# helmfile-bug-repro

Helmfile --state-values-set does not work in gotmpl.

Run `helmfile template` and see that image tag and the namespace successfully changed to `test2` as you would expect because override.yaml

Then, run `helmfile template --state-values-set ns=test3`

You can see that while namespace changed to test3, image tag did not and it stayed as test2.

Expected behaviour is that helmfile applies --state-values-set overrides in gotmpl files the same way it does for helmfile.yaml
