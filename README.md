# Implementation Guide CDA FHIR Maps

This Implementation Guide provides maps to transform between CDA and FHIR and back.

The source of the maps are located in ./input/maps

## Development

Clone this project https://github.com/ahdis/cda-fhir-maps/.

Open it with VSCode (RESTClient extension needs to be installed).

Download matchbox-0.4.0-SNAPSHOT.jar from https://github.com/ahdis/matchbox/releases/tag/0.4.0 into the main directory of the project cda-fhir-maps.

You need to download and install the package to your package cache the first time.

Mac:
```
java -cp matchbox-0.4.0-SNAPSHOT.jar -Dloader.main=ch.ahdis.matchbox.util.PackageCacheInitializer org.springframework.boot.loader.PropertiesLauncher -id hl7.fhir.cda -v dev -tgz http://build.fhir.org/ig/ahdis/cda-core-2.0/branches/pullrequests/package.tgz -desc hl7.fhir.cda
java -cp matchbox-0.4.0-SNAPSHOT.jar -Dloader.main=ch.ahdis.matchbox.util.PackageCacheInitializer org.springframework.boot.loader.PropertiesLauncher -id ch.fhir.ig.ch-epr-term -v current -tgz http://build.fhir.org/ig/hl7ch/ch-epr-term/package.tgz -desc ch.fhir.ig.ch-epr-term
java -cp matchbox-0.4.0-SNAPSHOT.jar -Dloader.main=ch.ahdis.matchbox.util.PackageCacheInitializer org.springframework.boot.loader.PropertiesLauncher -id ch.fhir.ig.ch-core -v current -tgz http://build.fhir.org/ig/hl7ch/ch-core/package.tgz -desc ch.fhir.ig.ch-core
java -cp matchbox-0.4.0-SNAPSHOT.jar -Dloader.main=ch.ahdis.matchbox.util.PackageCacheInitializer org.springframework.boot.loader.PropertiesLauncher -id ch.fhir.ig.ch-emed -v current -tgz http://build.fhir.org/ig/hl7ch/ch-emed/package.tgz -desc ch.fhir.ig.ch-emed
```

Windows:
```
java -cp matchbox-0.4.0-SNAPSHOT.jar -D"loader.main=ch.ahdis.matchbox.util.PackageCacheInitializer" org.springframework.boot.loader.PropertiesLauncher -id hl7.fhir.cda -v dev -tgz http://build.fhir.org/ig/ahdis/cda-core-2.0/branches/pullrequests/package.tgz -desc hl7.fhir.cda
java -cp matchbox-0.4.0-SNAPSHOT.jar -D"loader.main=ch.ahdis.matchbox.util.PackageCacheInitializer" org.springframework.boot.loader.PropertiesLauncher -id ch.fhir.ig.ch-epr-term -v current -tgz http://build.fhir.org/ig/hl7ch/ch-epr-term/package.tgz -desc ch.fhir.ig.ch-epr-term
java -cp matchbox-0.4.0-SNAPSHOT.jar -D"loader.main=ch.ahdis.matchbox.util.PackageCacheInitializer" org.springframework.boot.loader.PropertiesLauncher -id ch.fhir.ig.ch-core -v current -tgz http://build.fhir.org/ig/hl7ch/ch-core/package.tgz -desc ch.fhir.ig.ch-core
java -cp matchbox-0.4.0-SNAPSHOT.jar -D"loader.main=ch.ahdis.matchbox.util.PackageCacheInitializer" org.springframework.boot.loader.PropertiesLauncher -id ch.fhir.ig.ch-emed -v current -tgz http://build.fhir.org/ig/hl7ch/ch-emed/package.tgz -desc ch.fhir.ig.ch-emed
```

Start the matchbox.
```
java -jar matchbox-0.4.0-SNAPSHOT.jar  
```

## Transform documents between CDA and FHIR and back
Open **cdatofhir.http** and **fhirtocda.http** from the main directory with VSCode. 
* Choose @host = http://localhost:8080/r4  
* Add the maps to matchbox (Step 1 to 3).
* Transform your document (Examples shown in Step 5).


## Transform eMedication documents between CDA and FHIR and back
For eMedication documents you need an additional map, which is added to the matchbox in Step 4 (do Step 1-4).
For the transformation of the required document type open following (Examples shown in Step 5):

* Medication Card document: cdatofhir_card.http, fhirtocda_card.http
* Medication Dispense document: cdatofhir_dispense.http, fhirtocda_dispense.http
* Medication Prescription document: cdatofhir_prescription.http, fhirtocda_prescription.http