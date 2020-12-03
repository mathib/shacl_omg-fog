## Example SHACL shapes related to OMG/FOG geometry

### Introduction

The [W3C SHACL standard](https://www.w3.org/TR/shacl/) contains a methodology for defining shape constraints to validate content of RDF graphs. 
In addition, the SHACL standard specifies a uniform validation report in RDF.

### Content of this repository

The repository contains three Turtle (.ttl) documents:

- `shaclShapes.ttl` contains the shapes graph, i.e. 20 different shapes corresponding to 8 shape conditions expressed in human language
- `exampleDataset.ttl` reflects an example dataset that violates each shape to demonstrate them
- `validationReport.ttl` contains the standardized SHACL report

The ontologies folder contains snapshots of the [OMG](https://w3id.org/omg#), [FOG](https://w3id.org/fog#) and [BOT](https://w3id.org/bot#) ontologies.

### Reproduce the report in a SHACL engine

The below enumerated steps can be followed to reproduce the validation report using the above SHACL shapes and example dataset using the Stardog v7.2.0 engine:

1. Load `shaclShapes.ttl` and `exampleDataset.ttl` in the same Stardog database, e.g. "shacl-testdb"
2. Load the OMG, FOG and BOT ontologies from the ontologies folder
3. Execute the validation via the Stardog API, e.g. using the command line ([Stardog doc](https://www.stardog.com/docs/man/icv-report)):
`stardog icv report --reasoning shacl-testdb`