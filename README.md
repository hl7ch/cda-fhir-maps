# Implementation Guide

This implementation Guide provides maps to transform between CDA and FHIR and back.

The source of the maps are located in ./input/maps

## development

With cdatofhir.http and fhirtocda.http you can upload the maps to matchbox.

Download matchbox-x.jar from https://github.com/ahdis/matchbox/releases/ into this directory.

You need to download and install the package to your package cache the first time.

mac:
```
java -cp matchbox-0.4.0-SNAPSHOT.jar -Dloader.main=ch.ahdis.matchbox.util.PackageCacheInitializer org.springframework.boot.loader.PropertiesLauncher -id hl7.fhir.cda -v dev -tgz http://build.fhir.org/ig/ahdis/cda-core-2.0/branches/pullrequests/package.tgz -desc hl7.fhir.cda
java -cp matchbox-0.4.0-SNAPSHOT.jar -Dloader.main=ch.ahdis.matchbox.util.PackageCacheInitializer org.springframework.boot.loader.PropertiesLauncher -id ch.fhir.ig.ch-epr-term -v current -tgz http://build.fhir.org/ig/hl7ch/ch-epr-term/package.tgz -desc ch.fhir.ig.ch-epr-term
java -cp matchbox-0.4.0-SNAPSHOT.jar -Dloader.main=ch.ahdis.matchbox.util.PackageCacheInitializer org.springframework.boot.loader.PropertiesLauncher -id ch.fhir.ig.ch-core -v current -tgz http://build.fhir.org/ig/hl7ch/ch-core/package.tgz -desc ch.fhir.ig.ch-core
java -cp matchbox-0.4.0-SNAPSHOT.jar -Dloader.main=ch.ahdis.matchbox.util.PackageCacheInitializer org.springframework.boot.loader.PropertiesLauncher -id ch.fhir.ig.ch-emed -v current -tgz http://build.fhir.org/ig/hl7ch/ch-emed/package.tgz -desc ch.fhir.ig.ch-emed
```

windows:
```
java -cp matchbox-0.4.0-SNAPSHOT.jar -D"loader.main=ch.ahdis.matchbox.util.PackageCacheInitializer" org.springframework.boot.loader.PropertiesLauncher -id hl7.fhir.cda -v dev -tgz http://build.fhir.org/ig/ahdis/cda-core-2.0/branches/pullrequests/package.tgz -desc hl7.fhir.cda
java -cp matchbox-0.4.0-SNAPSHOT.jar -D"loader.main=ch.ahdis.matchbox.util.PackageCacheInitializer" org.springframework.boot.loader.PropertiesLauncher -id ch.fhir.ig.ch-epr-term -v current -tgz http://build.fhir.org/ig/hl7ch/ch-epr-term/package.tgz -desc ch.fhir.ig.ch-epr-term
java -cp matchbox-0.4.0-SNAPSHOT.jar -D"loader.main=ch.ahdis.matchbox.util.PackageCacheInitializer" org.springframework.boot.loader.PropertiesLauncher -id ch.fhir.ig.ch-core -v current -tgz http://build.fhir.org/ig/hl7ch/ch-core/package.tgz -desc ch.fhir.ig.ch-core
java -cp matchbox-0.4.0-SNAPSHOT.jar -D"loader.main=ch.ahdis.matchbox.util.PackageCacheInitializer" org.springframework.boot.loader.PropertiesLauncher -id ch.fhir.ig.ch-emed -v current -tgz http://build.fhir.org/ig/hl7ch/ch-emed/package.tgz -desc ch.fhir.ig.ch-emed
```

Clone the project https://github.com/ahdis/cda-fhir-maps/

Open it with VSCode (RESTClient extension needs to be installed) and start the matchbox. 

```
java -jar matchbox-0.4.0-SNAPSHOT.jar  
```

Open cdatofhir.http and fhirtocda.http from the main directory with VSCode. Add the maps (Step 1 to 5) and transform the examples.
