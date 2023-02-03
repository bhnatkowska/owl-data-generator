# owl-data-generator

This repository contains a datastore demonstrating input/output/configuration of the owl-data-generator tool.
input - examples of OWL2 ontologies for which data are generated
output - enriched ontologies with data generated according to configuration settings (kept in a yaml file)
dictionary - example glossary definitions used for generation process
configuration - automatically generated configurations by the owl-data-generator for the PDGF tool
schema - automatically generated schema  by the owl-data-generatorfor the PDGF tool 

The runnable version of the tool (jar file) can be downlad from:
https://drive.google.com/file/d/1ao4DT32x6kEOrJbhGPG-YcyLNoXX63Tx/view?usp=sharing

### owl-data-generator dependencies
#### Java SDK 15
Can be download from https://openjdk.java.net lub https://www.oracle.com/java/technologies/javase/jdk15-archive-downloads.html.
#### PDGF 2.7
A license required; can be obtain by a personal contact with info@bankmark.de 
More info: https://www.bankmark.de/products-and-services/pdgf/.

### Running instruction
#### Data generation
1. Prepare a configuration file and store it in the location `path_to_configuration_file` (set in the yaml configuration file, examples available)
2. Copy the input ontology to the "input" folder (set in the yaml configuration file)
3. In the console run the command:
  java -jar ontology-data-generator.jar <input_ontology_file> --spring.config.location=<path_to_configuration_file>
Generation results will be available in the "output" folder (set in the yaml configuration file).

#### Metrics calculation
In the console run the command:
  java -jar ontology-data-generator.jar <input_ontology_file> --spring.config.location=<path_to_configuration_file> calculate-metrics
####
