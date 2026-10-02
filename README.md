# OHT schema

The open schema for the [Online Harms Taxonomy Library](https://ohtl.org) (OHTL). Every taxonomy the Library publishes is mapped to it, so that categories from different publishers can be compared and linked.

## Approach

The schema is built on [SKOS](https://www.w3.org/TR/skos-reference/), the W3C standard for concept schemes, with [Dublin Core](https://www.dublincore.org/specifications/dublin-core/dcmi-terms/) terms for provenance.

| Taxonomy feature | Modelled as |
|---|---|
| A taxonomy or typology | `skos:ConceptScheme` |
| A category within it | `skos:Concept` |
| Hierarchy | `skos:broader` / `skos:narrower` |
| Definitions and examples | `skos:definition` / `skos:example` |
| Crosswalks between taxonomies | `skos:exactMatch` / `skos:closeMatch` / `skos:broadMatch` |

Where SKOS has no suitable term, the schema adds a small OHT extension. Likely candidates include whether text is statutory or a publisher's interpretation, examples of what a category does not cover, pinpoint references into a source document, and which edition of a document a citation refers to. Established vocabularies are always preferred to new terms.

The schema grows as sources are added, rather than being designed in full up front. Two rules make this safe:

- **Stable identifiers.** A published IRI never changes or disappears. Terms that are no longer needed are deprecated, not removed.
- **0.x releases.** Releases are numbered 0.x until the schema settles, so anything may still change between them.

## Releases

No release has been published yet. The first, 0.1, will be drafted from the first source, Ofcom's Guidance on Content Harmful to Children (April 2025).

Releases will be GitHub releases with semantic version tags (`v0.1.0` and so on). Pin a release rather than tracking `main`. Each taxonomy in [oht-library/taxonomies](https://github.com/oht-library/taxonomies) records the schema version it conforms to.

Planned layout:

```
ontology/   OHT extension terms (Turtle)
shapes/     SHACL shapes for validation, if adopted
```

## Licence

The licence has not been chosen yet. It will allow others to reuse the schema in their own knowledge graphs, with attribution at most.

## Contact

Questions and suggestions are welcome: open an issue or email [contact@ohtl.org](mailto:contact@ohtl.org).
