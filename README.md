Setup steps:

First follow setting up the catalog and sample broker: https://github.com/spadgett/origin-web-catalog/wiki/Running-the-catalog-with-the-%22UPS%22-sample-broker

Running template broker: https://github.com/spadgett/origin-web-catalog/wiki/Running-the-Catalog-with-the-Template-Broker

Apply image-stream updates (nodejs):
  oc apply -f https://raw.githubusercontent.com/openshift/origin/master/examples/image-streams/image-streams-rhel7.json -n openshift

Apply image-stream updates (java-s2i):
  oc apply -f https://raw.githubusercontent.com/jboss-openshift/application-templates/master/openjdk/openjdk18-web-basic-s2i.json -n openshift

  
