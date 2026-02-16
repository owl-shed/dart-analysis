# Dart analysis

<!-- Do not put the link/image nested tags on new lines as that will count the links as having whitespace which changes the rendering -->

<p align=center>
  <a title="A link to the latest version of the main pub.dev package for the project." href="https://pub.dev/packages/owl_analysis"><img alt="A status badge for the latest version of the main pub.dev package for the project." src="https://img.shields.io/pub/v/owl_analysis?logo=dart&logoColor=%230175C2&labelColor=%23d7d7d7"></a>
  <a title="A link to the score rating of the latest version of the main pub.dev package for the project." href="https://pub.dev/packages/owl_analysis/score"><img alt="A status badge for the score rating of the latest version of the main pub.dev package for the project." src="https://img.shields.io/pub/points/owl_analysis?logo=dart&logoColor=%230175C2&labelColor=%23d7d7d7&color=0175C2"></a>
  <a title="A link to the likes for the latest version of the main pub.dev package for the project." href="https://pub.dev/packages/owl_analysis/score"><img alt="A status badge for the likes for the latest version of the main pub.dev package for the project." src="https://img.shields.io/pub/likes/owl_analysis?logo=dart&logoColor=%230175C2&labelColor=%23d7d7d7"></a>
</p>

<p align="center"> <!-- Organisation -->
  <a title="A link to the OwlDomain Discord server." href="https://discord.gg/eXXnjTUPV2"><img alt="Status badge for the OwlDomain discord server." src="https://img.shields.io/discord/1411024983550853162?style=social&logo=discord&label=discord&link=https%3A%2F%2Fdiscord.gg%eXXnjTUPV2"></a>
</p>

---

A package for [owl-shed](https://github.com/owl-shed) analysis related things,
at least for the Dart projects.

This package is a set of lints and analyzer options, currently it only enables
the existing lints *(it doesn't add any custom ones yet)*, but that may change.

> [!IMPORTANT]
> This package is very opinionated, and it may change depending on how I feel
> in the future, lint changes **WILL NOT** be marked as breaking changes.

During the time that I've spent looking through every dart lint, I've realised
that they are very bad at naming them, and in some cases also documenting them,
and so I would actually encourage you to have a read through them.

I'd also like to encourage you to look at the source for this package, at the
very least the `general.yaml` file, as I've mostly included *(informal)*
comments regarding each one of my choices as to why an option was enabled or
disabled. As well as showing which lints are enabled by the
`core`, `recommended` and `flutter` lint packages.


## Usage

In order to use this package, install it as a `dev_dependency`, and then use
the `include` syntax to choose from one of the following:

- `general.yaml` - Use for general applications.
- `web.yaml` - Use for web applications.
- `package.yaml` - Use when you're making a custom package.

Then additionally, you can do **an extra** `include` to specify `experimental`,
which will also enable some of the dart lints that are still marked as
experimental.

### Example

```yaml
# In analysis_options.yaml
include: package:owl_analysis/general.yaml

# Or
include:
  - package:owl_analysis/package.yaml
  - package:owl_analysis/experimental.yaml
```


## Usual lints

The package also automatically includes:

```yaml
include:
  - package:lints/recommended.yaml # Implicitly includes the core.yaml lints too.
  - package:flutter_lints/flutter.yaml
```

This means that you shouldn't need to bother with changing them or having
complicated lint lists, you just add this package, choose one of the options
and you're good to go.


## Overrides

The `core.yaml` options are never overwritten to make sure that
[`pub.dev`](https://pub.dev) doesn't ruin the
[package ratings](https://pub.dev/help/scoring) *(I also didn't see any reason
to change them).*

The
[`prefer_adjacent_string_concatenation`](https://dart.dev/tools/linter-rules/prefer_adjacent_string_concatenation)
lint *(from `lints/recommended.yaml`)* however has been changed because
honestly who the heck thought this was even a good idea. I certainly don't, and
never will.


## Development

This package is being developed on the `develop` branch, the *(default)* `main`
branch will only be updated either when it's absolutely necessary, or when
there's a new release.
