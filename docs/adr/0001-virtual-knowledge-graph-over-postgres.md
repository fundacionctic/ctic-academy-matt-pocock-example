# Virtual knowledge graph over PostgreSQL

The knowledge graph of each Digital Twin is not stored as triples. PostgreSQL holds the extracted building data in relational tables, and Ontop exposes it as a virtual RDF graph in the BOT ontology through a SPARQL endpoint. The simulation adapter gets its inputs only through that SPARQL endpoint. This follows the architecture already recorded by CTIC for the SPHEERE Digital Infrastructure. That architecture has one source of truth for tables, time series and future cross-building queries, avoids running a separate graph database, and adds a reasoner only when a use case needs one.

## Considered Options

- **Materialised graph (rdflib, stored as Turtle or in a triple store).** This was the expectation of SPHEERE energy modellers, who worried that building a graph on demand could be slow. It was rejected because two copies of the same data drift apart, and synthetic models are too small for query speed to matter. If speed becomes a problem with real models, materialising Ontop's output is an option to add later, not a reason to change the design now.
- **PostgreSQL only, no RDF.** Simpler, but the "knowledge graph" would then exist in name only. Reading simulation inputs through SPARQL is what makes the graph the boundary between the IFC data and the engine.

## Consequences

Every new property the engine needs requires both a table column and an Ontop mapping. Adding a triple store to "fix" this cost goes against this decision.
