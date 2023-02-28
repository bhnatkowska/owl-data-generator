# owl-data-generator

This repository contains a datastore demonstrating input/output/configuration of the owl-data-generator tool.
The tool generates instances for a given OWL 2 domain ontology based on configuration and external data sources (dictionaries).

Datastore content:
- yaml files - example configurations for test ontologies (see input)
- datastore/input - examples of OWL2 ontologies for which data are generated
- datastore/output - enriched ontologies with data generated according to configuration settings (kept in a yaml file)
- datastore/dictionary - example glossary definitions used for generation process
- datastore/configuration - automatically generated configurations by the owl-data-generator for the PDGF tool
- datastore/schema - automatically generated schema  by the owl-data-generatorfor the PDGF tool 

The runnable version of the tool (jar file) can be downladed from:
https://drive.google.com/file/d/1ao4DT32x6kEOrJbhGPG-YcyLNoXX63Tx/view?usp=sharing

### owl-data-generator dependencies
#### Java SDK 15
Can be download from https://openjdk.java.net lub https://www.oracle.com/java/technologies/javase/jdk15-archive-downloads.html.
#### PDGF 2.7
A license required; can be obtain by a personal contact with info@bankmark.de 
More info: https://www.bankmark.de/products-and-services/pdgf/.

### Running instruction
#### Initial tests
1. Create a folder, e.g. c:\Tmp and copy the jar file to it
2. Download the repository content to c:\Tmp
3. Open commant prompt and go to the c:\Tmp folder

##### Exemplary commands
Data generation for the Test ontology (scalefactor=1) - requires PDGF to be installed:

java -jar ontology-data-generator.jar test.owl --spring.config.location=./test_configuration_scale1.yml all

Data generation for the Test ontology (scalefactor=1) based on the previously generated data by the PDGF tool:

java -jar ontology-data-generator.jar test.owl --spring.config.location=./test_configuration_scale1.yml populate-data

Data generation for the Test ontology (scalefactor=1) based on the previously generated data by the PDGF tool with metrics calculation:

java -jar ontology-data-generator.jar test.owl --spring.config.location=./test_configuration_scale1.yml populate-data calc-metrics

Metrics calculation for the Test ontology (in the input folder):

java -jar ontology-data-generator.jar test.owl --spring.config.location=./test_configuration_scale1.yml calc-metrics

Data generation for the Univ-bench ontology (scalefactor=1) - requires PDGF to be installed:

java -jar ontology-data-generator.jar univ-bench.owl --spring.config.location=./univ_bench_configuration_scale1.yml all

Data generation for the Test ontology (scalefactor=1) based on the previously generated data by the PDGF tool:

java -jar ontology-data-generator.jar univ-bench.owl --spring.config.location=./univ_bench_configuration_scale1.yml populate-data

Data generation for the Test ontology (scalefactor=1) based on the previously generated data by the PDGF tool with metrics calculation:

java -jar ontology-data-generator.jar univ-bench.owl --spring.config.location=./univ_bench_configuration_scale1.yml populate-data calc-metrics

Metrics calculation for the Test ontology (in the input folder):

java -jar ontology-data-generator.jar univ-bench.owl --spring.config.location=./univ_bench_configuration_scale1.yml calc-metrics

#### Data generation for other ontologies (requires PDGF tool to be installed)
1. Prepare a configuration file and store it in the location `path_to_configuration_file` (set in the yaml configuration file, examples available)
2. Copy the input ontology to the "input" folder (set in the yaml configuration file)
6. In the console run the command:
  
  java -jar ontology-data-generator.jar <input_ontology_file> --spring.config.location=<path_to_configuration_file> all

Generation results will be available in the "output" folder (set in the yaml configuration file).

#### Metrics calculation
In the console run the command:
  
  java -jar ontology-data-generator.jar <input_ontology_file> --spring.config.location=<path_to_configuration_file> calc-metrics
####
