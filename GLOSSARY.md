# SPHEERE Digital Infrastructure

The software that holds a digital representation of each renovated building in the SPHEERE project, joining its BIM model, energy simulations and measured data through an ontology layer.

## Language

**Digital Infrastructure**:
The platform that hosts the Digital Twins of many buildings and the services that act on them.
_Avoid_: platform, digital platform, SPHEERE platform, data lake, KG PoC

**Building**:
A real or synthetic building that a Digital Twin represents.
_Avoid_: asset, site (BOT uses `bot:Site` for a different concept)

**Digital Twin**:
The digital representation of one Building: its knowledge graph, simulation models and data, held within the Digital Infrastructure.
_Avoid_: using "Digital Twin" for the platform as a whole

**Model Revision**:
One uploaded IFC model of a Digital Twin, kept unchanged once stored; the latest valid revision is the twin's current one.
_Avoid_: version, upload, model update

**Validation Report**:
The result of checking one Model Revision against the required information content, listing each requirement it fails.
_Avoid_: repair report, check result, errors

**Thermal Zone**:
The part of a building treated as a single volume at uniform temperature in an energy simulation; in v1, the whole building.
_Avoid_: logical zone, room, space

**Simulation Run**:
One execution of an energy simulation against a single Model Revision, together with its results.
_Avoid_: simulation, calculation, job

**Simulation Assumption**:
An input to a Simulation Run that does not come from the Model Revision, such as a temperature setpoint, and is always shown to the analyst as an assumption.
_Avoid_: default, parameter, setting

**Demonstrator**:
A real Building renovated in SPHEERE, such as Forua, Ruše or Sykies.
_Avoid_: pilot, demo case, case study
