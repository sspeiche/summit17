Setup steps:

First follow setting up the catalog and sample broker: https://github.com/spadgett/origin-web-catalog/wiki/Running-the-catalog-with-the-%22UPS%22-sample-broker

Running template broker: https://github.com/spadgett/origin-web-catalog/wiki/Running-the-Catalog-with-the-Template-Broker

Apply image-stream updates (nodejs):
  oc apply -f https://raw.githubusercontent.com/openshift/origin/master/examples/image-streams/image-streams-rhel7.json -n openshift

Apply image-stream updates (java-s2i):
  oc apply -f https://raw.githubusercontent.com/jboss-openshift/application-templates/master/jboss-image-streams.json -n openshift

See pipeline samples

  oc new-app -f https://raw.githubusercontent.com/sspeiche/summit17


  oc adm policy add-cluster-role-to-user cluster-admin admin
