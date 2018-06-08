[<img src="http://sling.apache.org/res/logos/sling.png"/>](http://sling.apache.org)

 [![Build Status](https://builds.apache.org/buildStatus/icon?job=sling-org-apache-sling-nosql-generic-1.8)](https://builds.apache.org/view/S-Z/view/Sling/job/sling-org-apache-sling-nosql-generic-1.8) [![Test Status](https://img.shields.io/jenkins/t/https/builds.apache.org/view/S-Z/view/Sling/job/sling-org-apache-sling-nosql-generic-1.8.svg)](https://builds.apache.org/view/S-Z/view/Sling/job/sling-org-apache-sling-nosql-generic-1.8/test_results_analyzer/) [![Maven Central](https://maven-badges.herokuapp.com/maven-central/org.apache.sling/org.apache.sling.nosql.generic/badge.svg)](http://search.maven.org/#search%7Cga%7C1%7Cg%3A%22org.apache.sling%22%20a%3A%22org.apache.sling.nosql.generic%22) [![JavaDocs](https://www.javadoc.io/badge/org.apache.sling/org.apache.sling.nosql.generic.svg)](https://www.javadoc.io/doc/org.apache.sling/org.apache.sling.nosql.generic) [![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://www.apache.org/licenses/LICENSE-2.0) [![nosql](https://sling.apache.org/badges/group-nosql.svg)](https://github.com/apache/sling-aggregator/blob/master/docs/groups/nosql.md)&#32;[![contrib](http://sling.apache.org/badges/status-contrib.svg)](https://github.com/apache/sling-aggregator/blob/master/docs/status/contrib.md)

# Apache Sling NoSQL Generic Resource Provider

This module is part of the [Apache Sling](https://sling.apache.org) project.

Generic implementation of a Sling ResourceProvider that helps writing ResourceProviders using NoSQL databases as persistence.

The generic implementation helps mapping the resource data to document-oriented key-value NoSQL databases like MongoDB or Couchbase.

Features:

* Defines a simplified "NoSqlAdapter" concept that is implemented for each NoSQL database. It boils down to simple get/put/list operations. Query support is optional.
* Complete implementation of Resource, ResourceProvider, ResourceProviderFactory and ValueMap based on the NoSqlAdapter
* "Transaction management" of Sling CRUD (commit/revert methods) is implemented
* ValueMap supports String, Integer, Long, Double, Date, Calendar and InputStream/byte\[\] (binary data) and arrays of them. Date/Calendar and binary data is serialized to a string before storing, so the NoSQL databases have not to support them directly.
* Sends resource notifications via OSGi EventAdmin
* Provides a "tests" JAR that can be used for integration tests with NoSQL databases to test the own adapter implementation
* Can be mounted as root provider without any JCR at all
