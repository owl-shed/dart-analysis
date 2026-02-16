In order to use this package, install it as a `dev_dependency`, and then use
the `include` syntax to choose from one of the following:

- `general.yaml` - Use for general applications.
- `web.yaml` - Use for web applications.
- `package.yaml` - Use when you're making a custom package.

Then additionally, you can do **an extra** `include` to specify `experimental`,
which will also enable some of the dart lints that are still marked as
experimental.


```yaml
# In analysis_options.yaml
include: package:owlshed_analysis/general.yaml

# Or
include:
  - package:owlshed_analysis/package.yaml
  - package:owlshed_analysis/experimental.yaml
```
