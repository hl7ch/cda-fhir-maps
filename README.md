# Implementation Guide

This implementation Guide provides maps to transform between CDA and FHIR and back.

The source of the maps are located in ./input/maps

## development

with cdatofhir.http and fhirtocda.http you can upload the maps to matchbox

download matchbox-x.jar into this directory from https://github.com/ahdis/matchbox/releases/ to this directory

You need to download and install the package to you're package cache the first time.

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

clone the project https://github.com/ahdis/cda-fhir-maps/

open with VSCode, RESTClient extension needs to be installed and start the matchbox 

```
java -jar matchbox-0.4.0-SNAPSHOT.jar  
```

in the main diretory you can with now open with VSCode cdatofhir.http and fhirtocda.http you can add the maps (steps 1 to 5) and the transform the examples


