# FHIR mapping artefact used in transformation from STU3 CareConnect to R4 UKCore

## CareConnect to UKCore transform guidance

The FHIR artefacts in this repostiory are the source for the Implementation Guide at https://simplifier.net/stu3-careconnect-to-r4-ukcore-transform-guidance

## FML and StructureMap usage

This repository provides artefacts that can be used with the [validator_cli](https://github.com/hapifhir/org.hl7.fhir.core/releases/latest/download/validator_cli.jar) with the following invocation

```shell
java -jar validator_cli <input resource> -version 3.0 -to-version 4.0 -output <output resource>
```

This requires that the StructureMaps provided in this repo are in the local FHIR cache (e.g. ~/.fhir/packages/hl7.fhir.xver.r4#1.2.0/package/StructureMap-<resource>3to4).  See this [repo](https://github.com/declankieran-nhsd/hapi-fhir-3to4-demo) for more details on why this is required.
